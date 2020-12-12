---
description: 'Dowiedz się więcej na temat: printf_p parametry pozycyjne'
title: printf_p Parametry pozycyjne
ms.date: 11/04/2016
api_location:
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
helpviewer_keywords:
- _printf_p function, positional parameters
- printf_p function, positional parameters
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
ms.openlocfilehash: 2db76bc937e52b5945bf39cab1f47161fd3b162c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213432"
---
# <a name="printf_p-positional-parameters"></a>printf_p Parametry pozycyjne

Parametry pozycyjne zapewniają możliwość określenia przez liczbę argumentów, które mają zostać zastąpione w polu w ciągu formatu. Dostępne są następujące funkcje parametrów pozycyjnych `printf` :

| Niepozycyjne funkcje printf | Równoważne parametry pozycyjne |
|---|---|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|
|[sprintf —, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|
|[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|
|[vprintf, _vprintf_l, vwprintf, _vwprintf_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|
|[vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, \_ _vswprintf_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|

## <a name="how-to-specify-positional-parameters"></a>Jak określić parametry pozycyjne

### <a name="parameter-indexing"></a>Indeksowanie parametrów

Domyślnie, jeśli nie ma żadnego formatowania pozycyjnyego, funkcje pozycyjne zachowują się identycznie do tych, które nie są pozycjonowane. Należy określić parametr pozycyjny do formatowania przy użyciu `%n$` na początku specyfikatora formatu, gdzie `n` jest pozycją parametru do sformatowania na liście parametrów. Pozycja parametru rozpoczyna się od 1 dla pierwszego argumentu po ciągu formatu. Pozostała część specyfikatora formatu jest zgodna z tymi samymi regułami, które są zgodne ze `printf` specyfikatorem formatu. Aby uzyskać więcej informacji na temat formatu specfiers, zobacz [składnia specyfikacji formatowania: printf i wprintf Functions](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

Oto przykładowe formatowanie pozycyjne:

```C
_printf_p("%1$s %2$s", "November", "10");
```

Ten wydruk jest następujący:

```
November 10
```

Kolejność użytych liczb nie musi być zgodna z kolejnością argumentów. Na przykład jest to prawidłowy ciąg formatu:

```C
_printf_p("%2$s %1$s", "November", "10");
```

Ten wydruk jest następujący:

```
10 November
```

W przeciwieństwie do tradycyjnych ciągów formatowania, parametry pozycyjne mogą być używane więcej niż raz w ciągu formatu. Przykład:

```C
_printf_p("%1$d times %1$d is %2$d", 10, 100);
```

Ten wydruk jest następujący:

```
10 times 10 is 100
```

Wszystkie argumenty muszą być używane co najmniej raz w ciągu formatu. Maksymalna liczba parametrów pozycyjnych dozwolonych w ciągu formatu jest określona przez `_ARGMAX` .

### <a name="width-and-precision"></a>Szerokość i precyzja

Można użyć, `*n$` Aby określić parametr pozycyjny jako szerokość lub specyfikator dokładności, gdzie `n` jest pozycją parametru Width lub dokładności na liście parametrów. Pozycja wartości Width lub dokładności musi występować bezpośrednio po \* symbolu. Przykład:

```C
_printf_p("%1$*2$s","Hello", 10);
```

lub

```C
_printf_p("%2$*1$s", 10, "Hello");
```

### <a name="mixing-positional-and-non-positional-arguments"></a>Mieszanie argumentów pozycyjnych i niepozycyjnych

Parametry pozycyjne nie mogą być mieszane z parametrami niepozycyjnymi w tym samym ciągu formatu. Jeśli używane jest dowolne formatowanie pozycyjne, wszystkie specyfikatory formatu muszą używać formatowania pozycyjnego. Jednak `printf_p` funkcje pokrewne nadal obsługują parametry niepozycyjnye w ciągach formatujących, które nie zawierają parametrów pozycyjnych.

## <a name="example"></a>Przykład

```C
// positional_args.c
// Build by using: cl /W4 positional_args.c
// Positional arguments allow the specification of the order
// in which arguments are consumed in a formatting string.

#include <stdio.h>

int main()
{
    int     i = 1,
            j = 2,
            k = 3;
    double  x = 0.1,
            y = 2.22,
            z = 333.3333;
    char    *s1 = "abc",
            *s2 = "def",
            *s3 = "ghi";

    // If positional arguments are unspecified,
    // normal input order is used.
    _printf_p("%d %d %d\n", i, j, k);

    // Positional arguments are numbers followed by a $ character.
    _printf_p("%3$d %1$d %2$d\n", i, j, k);

    // The same positional argument may be reused.
    _printf_p("%1$d %2$d %1$d\n", i, j);

    // The positional arguments may appear in any order.
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);

    // Precision and width specifiers must be int types.
    _printf_p("%3$*5$f %2$.*4$f %1$*4$.*5$f\n", x, y, z, j, k);
}
```

```Output
1 2 3
3 1 2
1 2 1
abc def ghi
ghi abc def
333.333300 2.22 0.100
```

## <a name="see-also"></a>Zobacz także

[Składnia specyfikacji formatu: funkcje printf i wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)
