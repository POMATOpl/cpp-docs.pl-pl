---
description: Dowiedz się więcej o stałych liczbach całkowitych języka C
title: Stałe całkowite języka C
ms.date: 02/27/2018
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
ms.openlocfilehash: 1dbc22a2d4351dbd6d09f555a95380a1fd94619b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182193"
---
# <a name="c-integer-constants"></a>Stałe całkowite języka C

*Stała całkowita* to dziesiętna (podstawowa 10), ósemkowa (podstawowa 8) lub szesnastkowa (podstawowa 16) Liczba reprezentująca wartość całkowitą. Użyj stałych całkowitych do reprezentowania wartości całkowitych, których nie można zmienić.

## <a name="syntax"></a>Składnia

*Liczba całkowita — stała*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Decimal — stała* *Liczba całkowita sufiksu*<sub></sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ósemkowe — stała* *Liczba całkowita sufiksu*<sub></sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*niestandardowa* *Liczba całkowita z sufiksem*<sub></sub> szesnastkowym

*stała dziesiętna*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*niezerowe cyfry*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dziesiętna —* *cyfra* stała

*ósemkowa — stała*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**2,0**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ósemkowe — stała* *cyfra ósemkowa*

*stała szesnastkowa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;szesnastkowe *prefiksy* *szesnastkowe*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*szesnastkowe — stała* *szesnastkowa*

*prefiks szesnastkowy*: jedno z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0x**  **0x**

*niezerowe cyfry*: jedno z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**

*ósemkowa — cyfra*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7**

*cyfra szesnastkowa*: jedna z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**a b c d e f**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F**

*sufiks wartości całkowitej*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<sub>wybór</sub> *długich sufiksów* *bez znaku*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;sufiks *długi-Long-długi* *sufiks*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*niepodpisany sufiks* *64-bit-Integer-sufiks*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<sub>wybór</sub> *długiego* sufiksu *bez sufiksu*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<sub>wybór</sub> *długi-długi-* sufiks *bez sufiksu*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*64-bit-Integer-sufiks*

*niepodpisany sufiks*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**u U**

*długi sufiks*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**l L**

*długi-długi-sufiks*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**wszystkie wszystkie**

*64-bit-Integer-sufiks*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**i64 I64**

Sufiksy **I64** i **I64** są specyficzne dla firmy Microsoft.

Stałe całkowite są dodatnie, chyba że są poprzedzone znakiem minus ( **-** ). Znak minus jest interpretowany jako jednoargumentowy operator negacji arytmetycznej. (Zobacz [Jednoargumentowe operatory arytmetyczne](../c-language/unary-arithmetic-operators.md) , aby uzyskać informacje o tym operatorze).

Jeśli stała całkowita zaczyna się od **0x** lub **0x**, jest to wartość szesnastkowa. Jeśli zaczyna się od cyfry **0**, jest to ósemkowy. W przeciwnym razie przyjmuje się, że jest to wartość dziesiętna.

Następujące stałe całkowite są równoważne:

```C
28
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Znaki odstępu nie mogą oddzielić cyfr stałej całkowitej. W poniższych przykładach pokazano kilka prawidłowych stałych dziesiętnych, ósemkowych i szesnastkowych.

```C
    /* Decimal Constants */
    int                 dec_int    = 28;
    unsigned            dec_uint   = 4000000024u;
    long                dec_long   = 2000000022l;
    unsigned long       dec_ulong  = 4000000000ul;
    long long           dec_llong  = 9000000000LL;
    unsigned long long  dec_ullong = 900000000001ull;
    __int64             dec_i64    = 9000000000002I64;
    unsigned __int64    dec_ui64   = 90000000000004ui64;

    /* Octal Constants */
    int                 oct_int    = 024;
    unsigned            oct_uint   = 04000000024u;
    long                oct_long   = 02000000022l;
    unsigned long       oct_ulong  = 04000000000UL;
    long long           oct_llong  = 044000000000000ll;
    unsigned long long  oct_ullong = 044400000000000001Ull;
    __int64             oct_i64    = 04444000000000000002i64;
    unsigned __int64    oct_ui64   = 04444000000000000004uI64;

    /* Hexadecimal Constants */
    int                 hex_int    = 0x2a;
    unsigned            hex_uint   = 0XA0000024u;
    long                hex_long   = 0x20000022l;
    unsigned long       hex_ulong  = 0XA0000021uL;
    long long           hex_llong  = 0x8a000000000000ll;
    unsigned long long  hex_ullong = 0x8A40000000000010uLL;
    __int64             hex_i64    = 0x4a44000000000020I64;
    unsigned __int64    hex_ui64   = 0x8a44000000000040Ui64;
```

## <a name="see-also"></a>Zobacz też

[Stałe języka C](../c-language/c-constants.md)<br/>
