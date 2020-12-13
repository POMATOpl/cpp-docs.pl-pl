---
description: 'Dowiedz się więcej na temat: Klasa IOleControlImpl'
title: Klasa IOleControlImpl
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: e224f6f8db79c05cb8a774cd57517ba06108e592
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139428"
---
# <a name="iolecontrolimpl-class"></a>Klasa IOleControlImpl

Ta klasa zapewnia domyślną implementację `IOleControl` interfejsu i implementuje `IUnknown` .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IOleControlImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IOleControlImpl:: FreezeEvents](#freezeevents)|Wskazuje, czy kontener ignoruje lub akceptuje zdarzenia z formantu.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Wypełnia informacje o zachowaniu klawiatury formantu. Implementacja ATL zwraca E_NOTIMPL.|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Informuje formant, że co najmniej jedna z właściwości otoczenia kontenera zmieniła się. Implementacja ATL zwraca S_OK.|
|[IOleControlImpl::](#onmnemonic)|Informuje kontrolkę, że użytkownik naciśnie określone naciśnięcie klawisza. Implementacja ATL zwraca E_NOTIMPL.|

## <a name="remarks"></a>Uwagi

Klasa `IOleControlImpl` udostępnia domyślną implementację interfejsu [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) i implementuje ją `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a> IOleControlImpl:: FreezeEvents

W implementacji ATL, `FreezeEvents` zwiększa element członkowski danych klasy kontrolki, `m_nFreezeEvents` Jeśli `bFreeze` ma wartość true, i zmniejsza, `m_nFreezeEvents` Jeśli `bFreeze` ma wartość false.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Uwagi

`FreezeEvents` następnie zwraca S_OK.

Zobacz [IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) w Windows SDK.

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a> IOleControlImpl::GetControlInfo

Wypełnia informacje o zachowaniu klawiatury formantu.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Uwagi

Zobacz [IOleControl: GetControlInfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) w Windows SDK.

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a> IOleControlImpl::OnAmbientPropertyChange

Informuje formant, że co najmniej jedna z właściwości otoczenia kontenera zmieniła się.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IOleControl:: OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) w Windows SDK.

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a> IOleControlImpl::

Informuje kontrolkę, że użytkownik naciśnie określone naciśnięcie klawisza.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IOleControl::](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)<br/>
[Interfejsy formantów ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
