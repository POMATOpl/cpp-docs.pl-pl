---
description: 'Dowiedz się więcej na temat: _bstr_t:: Copy'
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 29ca965730dbcc22b4b725661ece68442d39aeba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229343"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Specyficzne dla firmy Microsoft**

Tworzy kopię hermetyzowania `BSTR` .

## <a name="syntax"></a>Składnia

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Parametry

*fCopy*<br/>
Jeśli **`true`** Funkcja **copy** zwraca kopię zawartej `BSTR` , w przeciwnym razie **kopia** zwraca rzeczywistą wartość BSTR.

## <a name="remarks"></a>Uwagi

Zwraca nowo przydzieloną kopię hermetyzowanego `BSTR` obiektu.

## <a name="example"></a>Przykład

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
