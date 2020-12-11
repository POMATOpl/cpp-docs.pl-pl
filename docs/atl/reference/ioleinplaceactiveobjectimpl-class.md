---
description: 'Dowiedz się więcej na temat: Klasa IOleInPlaceActiveObjectImpl'
title: Klasa IOleInPlaceActiveObjectImpl
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: 02f74e462dca2aac2749b8602281f40c8eacd0eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158195"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>Klasa IOleInPlaceActiveObjectImpl

Ta klasa zapewnia metody wspomagania komunikacji między kontrolką miejscową i jej kontenerem.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IOleInPlaceActiveObjectImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Włącza pomoc kontekstową. Implementacja ATL zwraca E_NOTIMPL.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Włącza Niemodalne okna dialogowe. Implementacja ATL zwraca S_OK.|
|[IOleInPlaceActiveObjectImpl:: GetWindow](#getwindow)|Pobiera uchwyt okna.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Powiadamia formant, gdy okno dokumentu kontenera jest aktywowane lub dezaktywowane. Implementacja ATL zwraca S_OK.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Powiadamia formant, gdy okno ramki najwyższego poziomu kontenera jest aktywowane lub dezaktywowane. Implementacja ATL zwraca|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Informuje kontrolkę, której potrzebuje, aby zmienić jej obramowanie. Implementacja ATL zwraca S_OK.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Przetwarza komunikaty klawisza skrótu menu z kontenera. Implementacja ATL zwraca E_NOTIMPL.|

## <a name="remarks"></a>Uwagi

Interfejs [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) pomaga komunikować się między kontrolką w miejscu a jego kontenerem; na przykład komunikacja stanu aktywnego kontrolki i kontenera oraz informowanie kontrolki potrzebnej do zmiany rozmiaru. Klasa `IOleInPlaceActiveObjectImpl` zapewnia domyślną implementację `IOleInPlaceActiveObject` i obsługuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a> IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

Włącza pomoc kontekstową.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) w Windows SDK.

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a> IOleInPlaceActiveObjectImpl::EnableModeless

Włącza Niemodalne okna dialogowe.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IOleInPlaceActiveObject:: EnableModeless](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) w Windows SDK.

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a> IOleInPlaceActiveObjectImpl:: GetWindow

Kontener wywołuje tę funkcję, aby uzyskać uchwyt okna kontrolki.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Uwagi

Niektóre kontenery nie będą współdziałać z kontrolką, która jest bez okna, nawet jeśli jest w tym oknie. W implementacji ATL, jeśli `CComControl::m_bWasOnceWindowless` element członkowski danych ma wartość true, funkcja zwraca E_FAIL. W przeciwnym razie, jeśli \* *phwnd* nie ma wartości null, `GetWindow` przypisuje *phwnd* do elementu członkowskiego danych klasy kontrolki `m_hWnd` i zwraca S_OK.

Zobacz [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) w Windows SDK.

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a> IOleInPlaceActiveObjectImpl::OnDocWindowActivate

Powiadamia formant, gdy okno dokumentu kontenera jest aktywowane lub dezaktywowane.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) w Windows SDK.

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a> IOleInPlaceActiveObjectImpl::OnFrameWindowActivate

Powiadamia formant, gdy okno ramki najwyższego poziomu kontenera jest aktywowane lub dezaktywowane.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) w Windows SDK.

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a> IOleInPlaceActiveObjectImpl::ResizeBorder

Informuje kontrolkę, której potrzebuje, aby zmienić jej obramowanie.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

### <a name="remarks"></a>Uwagi

Zobacz [IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) w Windows SDK.

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a> IOleInPlaceActiveObjectImpl::TranslateAccelerator

Przetwarza komunikaty klawisza skrótu menu z kontenera.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Wartość zwracana

Ta metoda obsługuje następujące wartości zwracane:

S_OK, jeśli komunikat został przetłumaczony pomyślnie.

S_FALSE, jeśli komunikat nie został przetłumaczony.

### <a name="remarks"></a>Uwagi

Zobacz [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Interfejsy formantów ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
