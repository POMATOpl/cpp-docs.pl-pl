---
description: Dowiedz się więcej o strukturze RuntimeClassBaseT
title: RuntimeClassBaseT — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 48f03a5d54eba455b60646ed47c48e228f07863e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135294"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parametry

*RuntimeClassTypeT*<br/>
Pole flag określające jeden lub więcej modułów wyliczających [RuntimeClassType —](runtimeclasstype-enumeration.md) .

## <a name="remarks"></a>Uwagi

Dostarcza metody pomocnika do `QueryInterface` operacji i uzyskiwania identyfikatorów interfejsów.

## <a name="members"></a>Elementy członkowskie

### <a name="protected-methods"></a>Metody chronione

Nazwa                                                         | Opis
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT:: AsIID —](#asiid)                           | Pobiera wskaźnik do określonego identyfikatora interfejsu.
[RuntimeClassBaseT:: Getimplementediids —](#getimplementediids) | Pobiera tablicę identyfikatorów interfejsów, które są implementowane przez określony typ.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`RuntimeClassBaseT`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a> RuntimeClassBaseT:: AsIID —

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ, który implementuje identyfikator interfejsu określony przez parametr *riid*.

*wprowadza*<br/>
Zmienna typu określona przez parametr szablonu *T*.

*riid*<br/>
Identyfikator interfejsu do pobrania.

*ppvObject*<br/>
Jeśli ta operacja zakończy się pomyślnie, wskaźnik do interfejsu określony przez parametr *riid*.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT, który opisuje błąd.

### <a name="remarks"></a>Uwagi

Pobiera wskaźnik do określonego identyfikatora interfejsu.

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a> RuntimeClassBaseT:: Getimplementediids —

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ parametru *Implements* .

*wprowadza*<br/>
Wskaźnik do typu określonego przez parametr *T*.

*IidCount —*<br/>
Maksymalna liczba identyfikatorów interfejsów do pobrania.

*IID*<br/>
Jeśli ta operacja zakończy się pomyślnie, tablica identyfikatorów interfejsów implementowanych przez typ *T*.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT, który opisuje błąd.

### <a name="remarks"></a>Uwagi

Pobiera tablicę identyfikatorów interfejsów, które są implementowane przez określony typ.
