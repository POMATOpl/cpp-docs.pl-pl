---
description: 'Dowiedz się więcej na temat: reprezentacja IEEE Floating-Point'
title: Odwzorowanie liczby zmiennoprzecinkowej IEEE
ms.date: 05/06/2019
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
ms.openlocfilehash: 9de48975ba13fae6117b095565f22265e28edf07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162654"
---
# <a name="ieee-floating-point-representation"></a>Odwzorowanie liczby zmiennoprzecinkowej IEEE

Język Microsoft C++ (MSVC) jest zgodny ze standardami cyfr IEEE. Standard IEEE-754 opisuje formaty zmiennoprzecinkowe w sposób przedstawiający rzeczywiste liczby sprzętu. Istnieje co najmniej pięć formatów wewnętrznych dla liczb zmiennoprzecinkowych, które są możliwe do zaprezentowania na sprzęcie przeznaczonym dla kompilatora MSVC. Kompilator używa tylko dwóch z nich. Formaty o *pojedynczej precyzji* (4-bajtowe) i *podwójnej precyzji* (8-bajtowe) są używane w MSVC. Pojedyncza precyzja jest zadeklarowana za pomocą słowa kluczowego **`float`** . Podwójna precyzja jest zadeklarowana za pomocą słowa kluczowego **`double`** . IEEE standard określa również format *połówkowej precyzji* (2-bajtowe) i *czterokrotnie Precision* (16-bajtowe) oraz formatu *podwójnej precyzji* (10-bajtowej), który implementuje niektóre kompilatory C i C++ jako **`long double`** Typ danych. W kompilatorze MSVC **`long double`** Typ danych jest traktowany jako typ odrębny, ale typ magazynu jest mapowany na **`double`** . Istnieje jednak obsługa obliczeń w języku wewnętrznym i wielojęzycznym przy użyciu innych formatów, w tym formatu podwójnej precyzji, który jest obsługiwany przez sprzęt.

Wartości są przechowywane w następujący sposób:

|Wartość|Przechowywane jako|
|-----------|---------------|
|Pojedyncza precyzja|bit znaku, 8-bitowy wykładnik, 23-bitowy mantysę|
|Podwójna precyzja|bit znaku, 11-bitowy wykładnik, 52-bitowy mantysę|

W formatach o pojedynczej precyzji i o podwójnej precyzji założono wiodącą 1 część ułamkową. Część ułamkowa jest nazywana *mantysę* (czasami znanym jako *mantysy*). Ten wiodący 1 nie jest przechowywany w pamięci, więc mantysy są w rzeczywistości 24 lub 53 bitów, nawet jeśli jest przechowywany jeden mniejszy bit. Format podwójnej precyzji w rzeczywistości przechowuje ten bit.

Wykładniki są rozdzielone połowami możliwych wartości. Oznacza to odjęcie tego bias od przechowywanego wykładniku w celu uzyskania rzeczywistego wykładnika. Jeśli przechowany wykładnik jest mniejszy niż wartość bias, w rzeczywistości jest to ujemna wykładnik.

Wykładniki są rozłączone w następujący sposób:

|Wykładnik|Obciążone przez|
|--------------|---------------|
|8-bitowa (pojedyncza precyzja)|127|
|11-bitowa (Podwójna precyzja)|1023|

Te wykładniki nie są potęgami dziesięciu; są one potęgami dwóch. Oznacza to, że 8-bitowe zapisane wykładniki mogą przyjmować od-127 do 127, przechowywane jako 0 do 254. Wartość 2<sup>127</sup> jest w przybliżeniu równa 10<sup>38</sup>, która jest rzeczywistym limitem pojedynczej precyzji.

Mantysę jest przechowywany jako ułamek binarny formularza 1.XXX... Ten ułamek ma wartość większą lub równą 1 i mniejszą niż 2. Liczby rzeczywiste są zawsze przechowywane w *znormalizowanym formacie*. Oznacza to, że mantysęa jest przesunięta w lewo, tak aby bit mantysę o wysokiej kolejności miał wartość zawsze 1. Ponieważ ten bit ma *zawsze* wartość 1, zakłada się, że nie jest on przechowywany w formatach o pojedynczej precyzji i podwójnej precyzji. Zakłada się, że punkt binarny (nie dziesiętny) jest po prawej stronie wiodącej wartości 1.

Format reprezentacji zmiennoprzecinkowej jest następujący:

|Format|bajt 1|bajt 2|bajt 3|bajt 4|...|bajt n|
|------------|------------|------------|------------|------------|---------|------------|
|Pojedyncza precyzja| `SXXXXXXX`|`XMMMMMMM`|`MMMMMMMM`|`MMMMMMMM`|||
|Podwójna precyzja|`SXXXXXXX`|`XXXXMMMM`|`MMMMMMMM`|`MMMMMMMM`|...|`MMMMMMMM`|

`S` reprezentuje bit znaku, jest to `X` bity wykładnika, a jest to `M` mantysę bity. Bit z lewej strony jest założono w formatach o pojedynczej precyzji i o podwójnej precyzji.

Aby prawidłowo przesunąć punkt binarny, najpierw należy rozwiązać ten wykładnik, a następnie przenieść punkt binarny w prawo lub w lewo do odpowiedniej liczby bitów.

## <a name="special-values"></a>Wartości specjalne

Formaty zmiennoprzecinkowe zawierają niektóre wartości, które są traktowane specjalnie.

### <a name="zero"></a>Zero

Nie można znormalizować wartości zero, co sprawia, że nie jest to możliwe w znormalizowanym formacie pojedynczej precyzji lub podwójnej precyzji. Specjalny wzorzec bitowy wszystkich zer reprezentuje 0. Możliwe jest również, aby reprezentować-0 jako zero z ustawionym bitem znaku, ale wartość 0 i 0 zawsze są porównywane jako równe.

### <a name="infinities"></a>Nieskończoności

Wartości + ∞ i − ∞ są reprezentowane przez wykładnikę wszystkich, a mantysę to zero. Dodatnie i ujemne są reprezentowane przy użyciu bitu znaku.

### <a name="subnormals"></a>Subnormalne

Istnieje możliwość reprezentowania liczby mniejszych wielkości niż najmniejsza liczba w znormalizowanym formacie. Są one nazywane numerami *normalnymi* lub *nienormalnymi* . Jeśli wykładnik ma wartość zero, a mantysę jest różna od zera, to niejawny wiodący bit mantysę jest uznawany za zero, a nie jeden. Precyzja wartości zwykłych jest określana jako liczba zer wiodących w mantysę.

### <a name="nan---not-a-number"></a>NaN — nie jest liczbą

Istnieje możliwość reprezentowania wartości, które nie są liczbami rzeczywistymi, na przykład 0/0, w formacie zmiennoprzecinkowym IEEE. Wartość tego rodzaju jest nazywana *NaN*. Wartość NaN jest reprezentowana przez wykładnik wszystkich i niezerowych mantysę. Istnieją dwa rodzaje NaNs, *quiet* Nans lub QNaNs oraz *sygnalizowanie* Nans lub SNaNs. Cicha NaNs zawiera jedną z nich w mantysę i jest przekazywana za pomocą wyrażenia. Reprezentują one wartość nieokreśloną, taką jak wynik dzielenia przez nieskończoność lub mnożenia nieskończoności przez zero. Sygnalizowanie NaNs mają wiodące zero w mantysę. Są one używane w przypadku operacji, które są nieprawidłowe, aby sygnalizować wyjątek sprzętu zmiennoprzecinkowego.

## <a name="examples"></a>Przykłady

Poniżej przedstawiono kilka przykładów w formacie o pojedynczej precyzji:

- Dla wartości 2 bit znaku jest równy zero. Plik wykładnik jest 128 lub 1000 0000 w postaci binarnej, która jest 127 plus 1. Przechowywany binarny mantysę to (1.) 000 0000 0000 0000 0000 0000, który ma implikowany wiodący znak 1 i binarny, więc rzeczywista mantysę to jeden.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |2|1 * 2<sup>1</sup>|0100 0000 0000 0000 0000 0000 0000 0000|0x40000000|

- Wartość-2. Analogicznie jak + 2, z tą różnicą, że jest ustawiony bit znaku. Ten sam element ma wartość true w przypadku wartości ujemnych dla wszystkich liczb zmiennoprzecinkowych formatu IEEE.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |-2|-1 * 2<sup>1</sup>|1100 0000 0000 0000 0000 0000 0000 0000|0xC0000000|

- Wartość 4. Ten sam mantysę, wykładnik zwiększa się o jeden (wartość bias to 129 lub 100 0000 1 w postaci binarnej.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |4|1 * 2<sup>2</sup>|0100 0000 1000 0000 0000 0000 0000 0000|0x40800000|

- Wartość 6. Ten sam wykładnik, mantysę jest większy o połowa. (1.) 100 0000... 0000 0000, ponieważ jest to ułamek binarny, is 1 1/2, ponieważ wartości ułamkowe cyfr to 1/2, 1/4, 1/8 i tak dalej.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |6|1,5<sup>* 2</sup>|0100 0000 1100 0000 0000 0000 0000 0000|0x40C00000|

- Wartość 1. Takie same mantysę jak inne uprawnienia dwóch, wykładnik, który jest mniejszy niż dwa o 127 lub 011 1111 1 w formacie binarnym.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |1|1 * 2<sup>0</sup>|0011 1111 1000 0000 0000 0000 0000 0000|0x3F800000|

- Wartość 0,75. Wykładnik z obciążeniem to 126, 011 1111 0 w postaci binarnej, a mantysę to (1.) 100 0000... 0000 0000, czyli 1 1/2.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |0,75|1,5 * 2<sup>-1</sup>|0011 1111 0100 0000 0000 0000 0000 0000|0x3F400000|

- Wartość 2,5. Dokładnie takie same, jak dwa, z wyjątkiem tego, że bit reprezentujący 1/4 jest ustawiony w mantysę.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |2.5|1,25<sup>* 2</sup>|0100 0000 0010 0000 0000 0000 0000 0000|0x40200000|

- 1/10 jest powtarzaną częścią binarną. Wartość mantysę jest nieco mniejsza niż 1,6, a wykładnik z podziałem wskazuje, że 1,6 ma być podzielona przez 16. (Jest 011 1101 1 w postaci binarnej, czyli 123 w formacie dziesiętnym). Prawdziwe wykładnika to 123-127 =-4, co oznacza, że współczynnik, przez który ma być mnożony, wynosi 2<sup>-4</sup> = 1/16. Składowa mantysę jest zaokrąglana w górę w ostatnim bit w wyniku próby reprezentowania niereprezentowanej liczby tak dokładnie, jak to możliwe. (Przyczyny, że 1/10 i 1/100 nie są dokładnie reprezentowane w postaci binarnej, są podobne do przyczyny, że 1/3 nie można dokładnie przedstawić w postaci dziesiętnej).

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |0,1|1,6 * 2<sup>– 4</sup>|0011 1101 1100 1100 1100 1100 1100 1101|0x3DCCCCCD|

- Zero jest szczególnym przypadkiem. Używa formuły dla minimalnej możliwej reprezentacji wartości dodatniej, która jest równa zero.

   |Wartość|Formuła|Reprezentacja binarna|Wartość szesnastkowa|
   |-|-|-|-|
   |0|1 * 2<sup>– 128</sup>|0000 0000 0000 0000 0000 0000 0000 0000|0x00000000|

## <a name="see-also"></a>Zobacz też

[Dlaczego liczby Floating-Point mogą utracić dokładnooć](why-floating-point-numbers-may-lose-precision.md)
