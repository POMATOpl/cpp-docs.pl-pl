---
description: Dowiedz się więcej o interfejsie IAxWinHostWindowLic
title: IAxWinHostWindowLic, interfejs
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: bf13d6f0209b982955fdf015ef47643c83b27eee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139649"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic, interfejs

Ten interfejs zapewnia metody manipulowania licencjonowaną kontrolką i jego obiektem hosta.

## <a name="syntax"></a>Składnia

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Elementy członkowskie

### <a name="methods"></a>Metody

|Nazwa|Opis|
|-|-|
|[Moje kontrolowane](#createcontrollic)|Tworzy licencjonowaną kontrolę i dołącza ją do obiektu hosta.|
|[CreateControlLicEx](#createcontrollicex)|Tworzy licencjonowaną kontrolę, dołącza ją do obiektu hosta i opcjonalnie konfiguruje procedurę obsługi zdarzeń.|

## <a name="remarks"></a>Uwagi

`IAxWinHostWindowLic` dziedziczy z [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) i dodaje metody, które obsługują tworzenie licencjonowanych kontrolek.

Zobacz [hostowanie formantów ActiveX przy użyciu biblioteki ATL AxHost](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) dla przykładu korzystającego z elementów członkowskich tego interfejsu.

## <a name="requirements"></a>Wymagania

Definicja tego interfejsu jest dostępna jako IDL lub C++, jak pokazano poniżej.

|Typ definicji|Plik|
|---------------------|----------|
|IDL|ATLIFace. idl|
|C++|ATLIFace. h (również zawarte w ATLBase. h)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> IAxWinHostWindowLic:: issterowane

Tworzy licencjonowaną kontrolę, inicjuje ją i hostuje w oknie identyfikowanym przez `hWnd` .

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parametry

*bstrLic*<br/>
podczas BSTR, który zawiera klucz licencji dla kontrolki.

### <a name="remarks"></a>Uwagi

Aby uzyskać opis pozostałych parametrów i wartości zwracanej, zobacz [IAxWinHostWindow:: IsControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) .

Wywołanie tej metody jest równoważne wywołaniu [IAxWinHostWindowLic:: CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Przykład

Zobacz [hostowanie formantów ActiveX przy użyciu biblioteki ATL AxHost](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) dla przykładu korzystającego z programu `IAxWinHostWindowLic::CreateControlLic` .

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> IAxWinHostWindowLic::CreateControlLicEx

Tworzy licencjonowany formant ActiveX, inicjuje go i hostuje w określonym oknie, podobnie jak [IAxWinHostWindow:: IsControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parametry

*bstrLic*<br/>
podczas BSTR, który zawiera klucz licencji dla kontrolki.

### <a name="remarks"></a>Uwagi

Aby uzyskać opis pozostałych parametrów i wartości zwracanej, zobacz [IAxWinHostWindow:: CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) .

### <a name="example"></a>Przykład

Zobacz [hostowanie formantów ActiveX przy użyciu biblioteki ATL AxHost](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) dla przykładu korzystającego z programu `IAxWinHostWindowLic::CreateControlLicEx` .
