---
title: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap
ms.date: 11/04/2016
apiname:
- _pctype
- _pwctype
- _wctype
- _mbctype
- _mbcasemap
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 75dc6bf07513133670ea182a23fb2b4d30c0cdd5
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702820"
---
# <a name="pctype-pwctype-wctype-mbctype-mbcasemap"></a>_pctype, _pwctype, _wctype, _mbctype, _mbcasemap

Tych zmiennych globalnych zawiera informacje używane przez funkcje klasyfikacji znaków. Są one tylko do użytku wewnętrznego.

## <a name="syntax"></a>Składnia

```
extern const unsigned short *_pctype;
extern const wctype_t *_pwctype;
extern const unsigned short _wctype[];
extern unsigned char _mbctype[];
extern unsigned char _mbcasemap[];
```

## <a name="remarks"></a>Uwagi

Informacje przedstawione w `_pctype`, `_pwctype`, i `_wctype` jest używana wewnętrznie przez [isupper, _isupper_l —, iswupper —, _iswupper_l —](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [islower, iswlower —, _islower_l —, _iswlower_l —](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [isdigit, iswdigit —, _isdigit_l —, _iswdigit_l —](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [isxdigit, iswxdigit —, _isxdigit_l —, _iswxdigit_l —](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), [isspace, iswspace —, _isspace_l —, _iswspace_l —](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md) , [isalnum, iswalnum —, _isalnum_l —, _iswalnum_l —](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), [ispunct, iswpunct —, _ispunct_l —, _iswpunct_l —](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), [isgraph, iswgraph —, _isgraph_l —, _iswgraph_l —](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md), [iscntrl, iswcntrl —, _iscntrl_l, — do _iswcntrl_l —](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md), [toupper, _toupper —, towupper —, _toupper_l —, _towupper_l —](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [tolower, _tolower —, towlower —, _tolower_l — i _towlower_l — ](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md) funkcji. Te funkcje powinny być używane zamiast uzyskiwanie dostępu do tych zmiennych globalnych.

Informacje przedstawione w `_mbctype` i `_mbcasemap` jest używana wewnętrznie przez [_ismbbkalnum —, _ismbbkalnum_l —](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [_ismbbkana —, _ismbbkana_l —](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), [_ismbbkpunct —, _ismbbkpunct_l —](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md), [_ismbbkprint —, _ismbbkprint_l —](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md), [_ismbbalpha —](reference/ismbbalpha-ismbbalpha-l.md), [_ismbbpunct —, _ismbbpunct_l —](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [_ismbbalnum —, _ismbbalnum_l — ](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md), [_ismbbprint —, _ismbbprint_l —](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md), [_ismbbgraph —, _ismbbgraph_l —](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md), [_ismbblead, _ismbblead_l —](../c-runtime-library/reference/ismbblead-ismbblead-l.md), [_ismbbtrail, _ismbbtrail_l —](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), [_ismbslead —, _ismbstrail —, _ismbslead_l —, _ismbstrail_l —](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md), [_ismbslead —, _ismbstrail —, _ismbslead_l — i _ismbstrail_l —](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md). Zamiast uzyskiwanie dostępu do zmiennych globalnych za pomocą tych funkcji.

## <a name="requirements"></a>Wymagania

Nie do użytku publicznego.

## <a name="see-also"></a>Zobacz też

[is, isw, procedury](../c-runtime-library/is-isw-routines.md)<br/>
[__pctype_func](../c-runtime-library/pctype-func.md)