---
description: 'Dowiedz się więcej na temat: _bstr_t:: operator ='
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 78447048a45567df603acf3af0bc51cefbdb187d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308786"
---
# <a name="_bstr_toperator-"></a>_bstr_t::operator =

**Specyficzne dla firmy Microsoft**

Przypisuje nową wartość do istniejącego `_bstr_t` obiektu.

## <a name="syntax"></a>Składnia

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parametry

*S2*<br/>
`_bstr_t`Obiekt, który ma zostać przypisany do istniejącego `_bstr_t` obiektu.

*S2*<br/>
Ciąg wielobajtowy, który ma zostać przypisany do istniejącego `_bstr_t` obiektu.

*S3*<br/>
Ciąg Unicode, który ma zostać przypisany do istniejącego `_bstr_t` obiektu.

*funkcję*<br/>
`_variant_t`Obiekt, który ma zostać przypisany do istniejącego `_bstr_t` obiektu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="example"></a>Przykład

Zobacz [_bstr_t:: Assign](../cpp/bstr-t-assign.md) , aby poznać przykład użycia **operatora =**.

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
