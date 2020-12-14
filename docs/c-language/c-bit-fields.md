---
description: 'Dowiedz się więcej o polach bitowych: C'
title: Pola bitowe języka C
ms.date: 11/04/2016
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
ms.openlocfilehash: e89f74fc68cad11eee63b3dd1101fa71e0b72e27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186957"
---
# <a name="c-bit-fields"></a>Pola bitowe języka C

Oprócz Deklaratory dla elementów członkowskich struktury lub Unii, struktura deklarator może również być określoną liczbą bitów o nazwie "pole bitowe". Jego długość jest ustawiana z deklarator dla nazwy pola za pomocą dwukropka. Pole bitowe jest interpretowane jako typ całkowity.

## <a name="syntax"></a>Składnia

*Struktura-deklarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Typ-specyfikator* *deklarator*<sub>opt</sub> **:** *wyrażenie stałe*

*Wyrażenie stałe* Określa szerokość pola w bitach. *Specyfikator typu* dla parametru `declarator` musi mieć **`unsigned int`** **`signed int`** wartość,, lub **`int`** , a *wyrażenie stałe* musi być nieujemną liczbą całkowitą. Jeśli wartość jest równa zero, deklaracja nie ma `declarator` . Tablice pól bitowych, wskaźników do pól bitowych i funkcji zwracających pola bitowe są niedozwolone. Opcjonalne `declarator` nazwy pola bitowego. Pola bitowe mogą być deklarowane tylko jako część struktury. Nie można zastosować operatora address-of ( **&** ) do składników pola bitowego.

Nie można odwoływać się do pól bitowych bez nazwy i ich zawartości w czasie wykonywania są nieprzewidywalne. Mogą służyć jako pola "fikcyjne" w celach wyrównania. Nienazwane pole bitowe, którego szerokość jest określona jako 0 gwarantuje, że magazyn dla elementu członkowskiego, który następuje po niej na *liście deklaracji struktury* , rozpoczyna się na **`int`** granicy.

Pola bitowe muszą być również wystarczająco długie, aby można było zawierać wzorzec bitowy. Na przykład te dwie instrukcje są niedozwolone:

```
short a:17;        /* Illegal! */
int long y:33;     /* Illegal! */
```

W tym przykładzie zdefiniowano dwuwymiarową tablicę struktur o nazwie `screen` .

```
struct
{
    unsigned short icon : 8;
    unsigned short color : 4;
    unsigned short underline : 1;
    unsigned short blink : 1;
} screen[25][80];
```

Tablica zawiera 2 000 elementów. Każdy element jest pojedynczą strukturą zawierającą cztery elementy członkowskie pola bitowego: `icon` , `color` , `underline` , i `blink` . Rozmiar każdej struktury wynosi dwa bajty.

Pola bitowe mają tę samą semantykę co typ liczba całkowita. Oznacza to, że pole bitowe jest używane w wyrażeniach w taki sam sposób jak zmienna tego samego typu podstawowego będzie używana, niezależnie od liczby bitów w polu bitowym.

**Specyficzne dla firmy Microsoft**

Pola bitowe zdefiniowane jako **`int`** są traktowane jako **`signed`** . Rozszerzenie Microsoft do standardu ANSI C zezwala na **`char`** i **`long`** typy (zarówno **`signed`** i **`unsigned`** ) dla pól bitowych. Nienazwane pola bitowe z typem podstawowym **`long`** , **`short`** lub **`char`** ( **`signed`** lub **`unsigned`** ) wymuszają wyrównanie do granicy właściwej dla typu podstawowego.

Pola bitowe są przypisywane w postaci liczby całkowitej od najmniej znaczącej do najbardziej znaczącego bitu. W poniższym kodzie

```
struct mybitfields
{
    unsigned short a : 4;
    unsigned short b : 5;
    unsigned short c : 7;
} test;

int main( void );
{
    test.a = 2;
    test.b = 31;
    test.c = 0;
}
```

bity można rozmieścić w następujący sposób:

```
00000001 11110010
cccccccb bbbbaaaa
```

Ponieważ rodzina 8086 procesorów przechowuje niską liczbę wartości całkowitych przed bajtem, liczba całkowita `0x01F2` powyżej byłaby przechowywana w pamięci fizycznej, `0xF2` a po niej `0x01` .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Deklaracje struktury](../c-language/structure-declarations.md)
