---
description: 'Dowiedz się więcej na temat: Klasa IPointerInactiveImpl'
title: Klasa IPointerInactiveImpl
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 0ee5c103582ff68c80edd36316179b47a1b7931d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139311"
---
# <a name="ipointerinactiveimpl-class"></a>Klasa IPointerInactiveImpl

Ta klasa implementuje `IUnknown` metody interfejsu [IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IPointerInactiveImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Pobiera bieżące zasady aktywacji dla obiektu. Implementacja ATL zwraca E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Powiadamia obiekt o przesunięciu wskaźnika myszy nad nim, wskazując, że obiekt może wyzwalać zdarzenia myszy. Implementacja ATL zwraca E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Ustawia wskaźnik myszy dla nieaktywnego obiektu. Implementacja ATL zwraca E_NOTIMPL.|

## <a name="remarks"></a>Uwagi

Obiekt nieaktywny to ten, który jest po prostu ładowany lub uruchomiony. W przeciwieństwie do aktywnego obiektu nieaktywny obiekt nie może odbierać komunikatów myszy i klawiatury systemu Windows. W ten sposób obiekty nieaktywne używają mniejszej ilości zasobów i są zwykle bardziej wydajne.

Interfejs [IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) umożliwia obiektowi obsługę minimalnego poziomu interakcji myszy, podczas gdy pozostaje nieaktywna. Ta funkcja jest szczególnie przydatna w przypadku formantów.

Klasa `IPointerInactiveImpl` implementuje `IPointerInactive` metody przez po prostu zwrócenie E_NOTIMPL. Jest to jednak implementowane `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a> IPointerInactiveImpl::GetActivationPolicy

Pobiera bieżące zasady aktywacji dla obiektu.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IPointerInactive:: GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) w Windows SDK.

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a> IPointerInactiveImpl::OnInactiveMouseMove

Powiadamia obiekt o przesunięciu wskaźnika myszy nad nim, wskazując, że obiekt może wyzwalać zdarzenia myszy.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IPointerInactive:: OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) w Windows SDK.

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a> IPointerInactiveImpl::OnInactiveSetCursor

Ustawia wskaźnik myszy dla nieaktywnego obiektu.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IPointerInactive:: OnInactiveSetCursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
