---
title: Stałe całkowite języka C | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eef5ba48d28b898ffc624d5790b0f414a8c112c3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389757"
---
# <a name="c-integer-constants"></a>Stałe całkowite języka C

*Stała całkowita* wartości dziesiętnej (o podstawie 10), ósemkowy (podstawa 8) lub liczbą szesnastkową (podstawa 16), która reprezentuje wartością całkowitą. Stałe całkowite umożliwia reprezentują wartości całkowite, których nie można zmienić.

## <a name="syntax"></a>Składnia

*stała całkowita*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub><br/>

*decimal — stała*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*nonzero-digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*decimal — stała* *cyfrę*<br/>

*ósemkowe stała*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ósemkowe stała* *-ósemkowego*<br/>

*Stała liczba szesnastkowa*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Prefiks szesnastkowy* *cyfrę szesnastkową*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Stała liczba szesnastkowa* *cyfrę szesnastkową*<br/>

*Prefiks szesnastkowy*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0x**  **0X**<br/>

*niezerowe cyfrowy*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**<br/>

*ósemkowego*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7**<br/>

*cyfrę szesnastkową*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**b c d e f**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F**<br/>

*integer-suffix*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sufiks niepodpisane* *long sufiks*<sub>opcjonalnych</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unsigned-suffix* *long-long-suffix*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unsigned-suffix* *64-bit-integer-suffix*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sufiks Long* *niepodpisane sufiks*<sub>opcjonalnych</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*long-long-suffix* *unsigned-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*64-bit-integer-suffix*<br/>

*sufiks niepodpisane*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**u U**<br/>

*sufiks Long*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**l L**<br/>

*Long long sufiksem*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ll LL**<br/>

*64-bitowe — liczba całkowita sufiks*: jeden z<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**komputerach komputerach 64 64**<br/>

**Komputerach 64** i **komputerach 64** sufiksy są specyficzne dla firmy Microsoft.

Stałe całkowite są dodatnie, chyba że są poprzedzone znakiem minus (**-**). Znak minus jest interpretowany jako Jednoargumentowy operator negacji arytmetyczne. (Zobacz [jednoargumentowe operatory arytmetyczne](../c-language/unary-arithmetic-operators.md) informacji dotyczących tego operatora.)

Jeśli zaczyna się od stałej całkowitej **0 x** lub **0 X**, jest szesnastkową. Jeśli zaczyna się od cyfry **0**, jest ósemkowe. W przeciwnym razie jest przyjmowana dziesiętną.

Następujące stałe całkowite są równoważne:

```C
28
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Żadne znaki odstępu można oddzielić cyfr całkowitą wartością stałą. Poniższe przykłady pokazują niektóre prawidłowych stałych decimal, ósemkowe i szesnastkowe.

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

## <a name="see-also"></a>Zobacz także

[Stałe języka C](../c-language/c-constants.md)<br/>
