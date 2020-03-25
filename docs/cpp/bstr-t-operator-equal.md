---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 5b7f499dd84a67020232aab84966647378daadad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181073"
---
# <a name="_bstr_toperator-"></a>_bstr_t::operator =

**Specyficzne dla firmy Microsoft**

Przypisuje nową wartość do istniejącego obiektu `_bstr_t`.

## <a name="syntax"></a>Składnia

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Parametry

*S2*<br/>
Obiekt `_bstr_t`, który ma zostać przypisany do istniejącego obiektu `_bstr_t`.

*S2*<br/>
Ciąg wielobajtowy, który ma zostać przypisany do istniejącego obiektu `_bstr_t`.

*S3*<br/>
Ciąg Unicode, który ma zostać przypisany do istniejącego obiektu `_bstr_t`.

*var*<br/>
Obiekt `_variant_t`, który ma zostać przypisany do istniejącego obiektu `_bstr_t`.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="example"></a>Przykład

Zobacz [_bstr_t:: Assign](../cpp/bstr-t-assign.md) , aby poznać przykład użycia **operatora =** .

## <a name="see-also"></a>Zobacz też

[_bstr_t, klasa](../cpp/bstr-t-class.md)
