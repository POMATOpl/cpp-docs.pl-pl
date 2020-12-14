---
description: 'Dowiedz się więcej na temat: limity przestawne'
title: Limity liczb zmiennoprzecinkowych
ms.date: 08/03/2018
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
ms.openlocfilehash: 92694ee605d7cec12d03d808168b095f5c9f447b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242590"
---
# <a name="floating-limits"></a>Limity liczb zmiennoprzecinkowych

**Specyficzne dla firmy Microsoft**

W poniższej tabeli wymieniono limity wartości stałych zmiennoprzecinkowych. Te limity są również zdefiniowane w standardowym pliku nagłówkowym \<float.h> .

## <a name="limits-on-floating-point-constants"></a>Limity dla stałych zmiennoprzecinkowych

|Stała|Znaczenie|Wartość|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|Liczba cyfr, q, takich jak liczba zmiennoprzecinkowa z cyframi dziesiętnymi q, może być zaokrąglana do reprezentacji zmiennoprzecinkowej i z powrotem bez utraty dokładności.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|Najmniejsza liczba dodatnia x, tak że x + 1,0 nie jest równa 1,0.|1.192092896 e-07F<br/>2.2204460492503131 e-016<br/>2.2204460492503131 e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|Liczba cyfr w podstawy określonym przez `FLT_RADIX` wartość w mantysę zmiennoprzecinkowej. Podstawy to 2; w związku z tym te wartości określają bity.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|Maksymalna reprezentacja liczby zmiennoprzecinkowej.|3.402823466 e + 38F<br/>1.7976931348623158 e + 308<br/>1.7976931348623158 e + 308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|Maksymalna liczba całkowita, taka jak 10 podniesiona do tej liczby, to reprezentacja liczby zmiennoprzecinkowej.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|Maksymalna liczba całkowita, która `FLT_RADIX` podniesiono do tej liczby, jest reprezentacją liczby zmiennoprzecinkowej.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|Minimalna wartość dodatnia.|1.175494351 e-38F<br/>2.2250738585072014 e-308<br/>2.2250738585072014 e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|Minimalna ujemna liczba całkowita, taka jak 10 podniesiono do tej liczby, jest reprezentacją liczby zmiennoprzecinkowej.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|Minimalna ujemna liczba całkowita, która `FLT_RADIX` podniesiono do tej liczby, jest reprezentacją liczby zmiennoprzecinkowej.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|Podstawy reprezentacji wykładnika.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|Tryb zaokrąglania dla dodawania zmiennoprzecinkowego.|1 (blisko)<br/>1 (blisko)<br/>1 (blisko)|

> [!NOTE]
> Informacje w tabeli mogą się różnić w przyszłych wersjach produktu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Limity liczb całkowitych](../cpp/integer-limits.md)
