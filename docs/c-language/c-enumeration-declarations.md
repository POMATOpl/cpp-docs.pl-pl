---
title: Deklaracje modułów wyliczających języka C
description: Deklaracje wyliczenia w języku programowania C.
ms.date: 10/02/2020
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
ms.openlocfilehash: b7df41475a630b9f6e1d735f5454f6d9601cdd16
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765208"
---
# <a name="c-enumeration-declarations"></a>Deklaracje modułów wyliczających języka C

Wyliczenie składa się z zestawu nazwanych stałych całkowitych. Deklaracja typu wyliczenia zawiera nazwę znacznika wyliczenia (opcjonalnie). I definiuje zestaw o nazwanych liczbach całkowitych (nazywany *zestawem wyliczenia*, *stałymi modułami*wyliczającymi, *modułami wyliczanymi*lub *elementami członkowskimi*). Zmienna typu wyliczenia przechowuje jedną z wartości zestawu wyliczenia zdefiniowanego przez ten typ.

Zmienne **`enum`** typu mogą być używane w wyrażeniach indeksowania oraz jako argumenty operacji wszystkich operatorów arytmetycznych i relacyjnych. Wyliczenia stanowią alternatywę dla `#define` dyrektywy preprocesora, dzięki czemu można generować wartości dla Ciebie i przestrzegać normalnych zasad określania zakresu.

W standardzie ANSI C, wyrażenia definiujące wartość stałej modułu wyliczającego zawsze mają **`int`** Typ. Oznacza to, że magazyn skojarzony ze zmienną wyliczenia jest magazynem wymaganym dla pojedynczej **`int`** wartości. Stała wyliczenia lub wartość typu wyliczeniowego może być używana wszędzie tam, gdzie język C zezwala na wyrażenie liczby całkowitej.

## <a name="syntax"></a>Składnia

*`enum-specifier`*:\
&emsp;**`enum`***`identifier`* <sub>opt</sub> **`{`** wybór *`enumerator-list`***`}`**\
&emsp;**`enum`** *`identifier`*

*`enumerator-list`*:\
&emsp;*`enumerator`*\
&emsp;*`enumerator-list`* **`,`** *`enumerator`*

*`enumerator`*:\
&emsp;*`enumeration-constant`*\
&emsp;*`enumeration-constant`* **`=`** *`constant-expression`*

*`enumeration-constant`*:\
&emsp;*`identifier`*

Opcjonalna *`identifier`* Nazwa typ wyliczeniowy zdefiniowany przez *`enumerator-list`* . Ten identyfikator jest często nazywany "tagiem" wyliczenia określonego przez listę. Specyfikator typu deklaruje jako `identifier` tag wyliczenia określony przez element *`enumerator-list`* niebędący opisem w tym miejscu:

```C
enum identifier
{
    // enumerator-list
}
```

*`enumerator-list`* Definiuje elementy członkowskie zestawu wyliczenia.

Jeśli deklaracja tagu jest widoczna, późniejsze deklaracje używające znacznika, ale pomijają *`enumerator-list`* Określ zadeklarowany wcześniej typ wyliczeniowy. Tag musi odwoływać się do zdefiniowanego typu wyliczenia i ten typ wyliczeniowy musi znajdować się w bieżącym zakresie. Ponieważ typ wyliczenia jest zdefiniowany w innym miejscu, *`enumerator-list`* nie pojawia się w tej deklaracji. Deklaracje typów pochodzących z wyliczeń i **`typedef`** deklaracji dla typów wyliczeniowych mogą użyć znacznika wyliczenia przed zdefiniowaniem typu wyliczenia.

Każdy *`enumeration-constant`* w *`enumerator-list`* nazwie ma wartość zestawu wyliczenia. Domyślnie pierwszy *`enumeration-constant`* jest skojarzony z wartością 0. Dalej *`enumeration-constant`* na liście jest skojarzona z wartością ( *`constant-expression`* + 1), chyba że jawnie skojarzenie jej z inną wartością. Nazwa *`enumeration-constant`* jest równoznaczna z jego wartością.

Można użyć, *`enumeration-constant`*  =  *`constant-expression`* Aby przesłonić domyślną sekwencję wartości. Oznacza to, że jeśli *`enumeration-constant`*  =  *`constant-expression`* pojawia się w *`enumerator-list`* , *`enumeration-constant`* jest skojarzony z wartością podaną przez *`constant-expression`* . *`constant-expression`* **`int`** Typ musi być wartością ujemną.

Do elementów członkowskich zestawu wyliczania są stosowane następujące reguły:

- Zestaw wyliczenia może zawierać zduplikowane wartości stałych. Można na przykład skojarzyć wartość 0 z dwoma różnymi identyfikatorami, na przykład członkowie o nazwach `null` i `zero` , w tym samym zestawie.

- Identyfikatory na liście wyliczenia muszą być różne od innych identyfikatorów w tym samym zakresie o tej samej widoczności. Zawiera zwykłe nazwy zmiennych i identyfikatory z innych list wyliczenia.

- Tagi wyliczenia przestrzegają normalnych reguł określania zakresu. Muszą one różnić się od innych tagów wyliczenia, struktury i Unii o tej samej widoczności.

## <a name="examples"></a>Przykłady

Te przykłady ilustrują deklaracje wyliczenia:

```C
enum DAY            /* Defines an enumeration type    */
{
    saturday,       /* Names day and declares a       */
    sunday = 0,     /* variable named workday with    */
    monday,         /* that type                      */
    tuesday,
    wednesday,      /* wednesday is associated with 3 */
    thursday,
    friday
} workday;
```

Domyślnie jest skojarzona wartość 0 `saturday` . Identyfikator `sunday` jest jawnie ustawiony na 0. Pozostałe identyfikatory domyślnie otrzymują wartości od 1 do 5.

W tym przykładzie wartość z zestawu `DAY` jest przypisana do zmiennej `today` .

```C
enum DAY today = wednesday;
```

Nazwa stałej wyliczenia służy do przypisywania wartości. Ponieważ `DAY` Typ wyliczeniowy został poprzednio zadeklarowany, konieczne jest tylko oznakowanie wyliczenia `DAY` .

Aby jawnie przypisać wartość całkowitą do zmiennej typu wyliczeniowego, należy użyć rzutowania typu:

```C
workday = ( enum DAY ) ( day_value - 1 );
```

To Rzutowanie jest zalecane w języku C, ale nie jest wymagane.

```C
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */
{
    false,     /* false = 0, true = 1 */
    true
};

enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */
```

Tę deklarację można również określić jako

```C
enum BOOLEAN { false, true } end_flag, match_flag;\
```

lub jako

```C
enum BOOLEAN { false, true } end_flag;
enum BOOLEAN match_flag;
```

Przykład wykorzystujący te zmienne może wyglądać następująco:

```C
if ( match_flag == false )
    {
     .
     .   /* statement */
     .
    }
    end_flag = true;
```

Można również zadeklarować nienazwane typy danych modułu wyliczającego. Nazwa typu danych jest pomijana, ale można zadeklarować zmienne. Zmienna `response` jest zmienną typu zdefiniowanego:

```C
enum { yes, no } response;
```

## <a name="see-also"></a>Zobacz też

[Wyliczenia](../cpp/enumerations-cpp.md)
