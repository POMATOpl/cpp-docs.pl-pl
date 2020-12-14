---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: QueryInterface'
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 6c6ff19227c920aade762af295942d8058a17ad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295344"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Specyficzne dla firmy Microsoft**

Wywołuje funkcję  elementu członkowskiego QueryInterface `IUnknown` w wskaźniku hermetyzowanego interfejsu.

## <a name="syntax"></a>Składnia

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>Parametry

*IID*<br/>
`IID` wskaźnika interfejsu.

*St*<br/>
Pierwotny wskaźnik interfejsu.

## <a name="remarks"></a>Uwagi

Wywołuje `IUnknown::QueryInterface` wskaźnik interfejsu hermetyzowanego z określonym `IID` i zwraca wynikowy wskaźnik interfejsu w *p*. Ta procedura zwraca wynik HRESULT wskazujący powodzenie lub niepowodzenie.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
