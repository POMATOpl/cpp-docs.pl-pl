---
description: 'Dowiedz się więcej na temat: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap'
title: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap
ms.date: 11/04/2016
api_name:
- _pctype
- _pwctype
- _wctype
- _mbctype
- _mbcasemap
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- pwctype
- pctype
- mbctype
- mbcasemap
- _mbcasemap
- _mbctype
- _pctype
- _wctype
- _pcwtype
helpviewer_keywords:
- _wctype function
- _pwctype function
- _pctype function
- _mbctype function
- wctype function
- pwctype function
- pctype function
- mbcasemap function
- mbctype function
- _mbcasemap function
ms.assetid: 7f5e1107-c43b-4b9b-b387-781e6d2373cb
ms.openlocfilehash: 4122d282b3b205af3d6fb67f9755f9c13c4bb5e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213458"
---
# <a name="_pctype-_pwctype-_wctype-_mbctype-_mbcasemap"></a>_pctype, _pwctype, _wctype, _mbctype, _mbcasemap

Te zmienne globalne zawierają informacje używane przez funkcje klasyfikacji znaków. Są one przeznaczone wyłącznie do użytku wewnętrznego.

## <a name="syntax"></a>Składnia

```
extern const unsigned short *_pctype;
extern const wctype_t *_pwctype;
extern const unsigned short _wctype[];
extern unsigned char _mbctype[];
extern unsigned char _mbcasemap[];
```

## <a name="remarks"></a>Uwagi

Informacje w `_pctype` , `_pwctype` i `_wctype` są używane wewnętrznie przez [IsUpper, _isupper_l, iswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [IsLower, iswlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [iscyfr, iswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), [isspace, iswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md), [isalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), ispunct, [iswpunct, _ispunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), _iswpunct_l, [isgraph, iswgraph,](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)_isgraph_l, _iswgraph_l, [iscntrl](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md) [](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), iswcntrl, _iscntrl_l, ToUpper, _iswcntrl_l [i _toupper](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md) . Te funkcje powinny być używane zamiast uzyskiwania dostępu do tych zmiennych globalnych.

Informacje zawarte w `_mbctype` i `_mbcasemap` są używane wewnętrznie przez [_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), [_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md), _ismbbkpunct_l, [_ismbbkprint,](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)_ismbbkprint_l, [_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md), [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md), [_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md), [_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md), [_ismbblead,](../c-runtime-library/reference/ismbblead-ismbblead-l.md)_ismbblead_l, _ismbbtrail [, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), _ismbslead, [_ismbstrail, _ismbslead_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md), _ismbstrail_l, [_ismbslead, _ismbstrail, _ismbslead_l i _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md). Użyj tych funkcji zamiast uzyskiwania dostępu do zmiennych globalnych.

## <a name="requirements"></a>Wymagania

Nie do użytku publicznego.

## <a name="see-also"></a>Zobacz też

[to, ISW, procedury](../c-runtime-library/is-isw-routines.md)<br/>
[__pctype_func](../c-runtime-library/pctype-func.md)
