---
description: 'Dowiedz się więcej na temat: _bstr_t:: Attach'
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: b3f29c8eaf81a492f7e3c4282227d3d6d246988e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229434"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Specyficzne dla firmy Microsoft**

Łączy `_bstr_t` otokę z `BSTR` .

## <a name="syntax"></a>Składnia

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Parametry

*s*<br/>
Element `BSTR` , który ma być skojarzony z lub przypisany do `_bstr_t` zmiennej.

## <a name="remarks"></a>Uwagi

Jeśli `_bstr_t` wcześniej była dołączona do innego `BSTR` , `_bstr_t` spowoduje to oczyszczenie `BSTR` zasobu, jeśli żadne inne zmienne nie `_bstr_t` używają `BSTR` .

## <a name="example"></a>Przykład

Zobacz [_bstr_t:: Assign](../cpp/bstr-t-assign.md) dla przykładu przy użyciu **dołączania**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
