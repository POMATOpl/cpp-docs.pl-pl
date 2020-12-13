---
description: 'Dowiedz się więcej na temat: Klasa CMessageMap'
title: Klasa CMessageMap
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: 90ecdc101071b84362d328558ff2e74cb9bbeb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141443"
---
# <a name="cmessagemap-class"></a>Klasa CMessageMap

Ta klasa umożliwia mapowanie komunikatów obiektu na dostęp przez inny obiekt.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMessageMap::P rocessWindowMessage](#processwindowmessage)|Uzyskuje dostęp do mapy komunikatów w `CMessageMap` klasie pochodnej.|

## <a name="remarks"></a>Uwagi

`CMessageMap` jest abstrakcyjną klasą bazową umożliwiającą dostęp do mapowań komunikatów obiektu przez inny obiekt. Aby obiekt mógł uwidaczniać mapy komunikatów, jego Klasa musi pochodzić od `CMessageMap` .

ATL używa `CMessageMap` do obsługi zawartych w systemie Windows i dynamicznego łańcucha map wiadomości. Na przykład każda klasa zawierająca obiekt [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) musi pochodzić od `CMessageMap` . Poniższy kod jest pobierany z przykładu [SubEdit](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) . Za pośrednictwem [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` Klasa automatycznie dziedziczy z `CMessageMap` .

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

Ponieważ zawarte okno, `m_EditCtrl` , będzie używać mapy komunikatów w klasie zawierającej, `CAtlEdit` pochodzi od `CMessageMap` .

Aby uzyskać więcej informacji na temat map wiadomości, zobacz [mapy komunikatów](../../atl/message-maps-atl.md) w artykule "klasy ATL".

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a> CMessageMap::P rocessWindowMessage

Uzyskuje dostęp do mapy komunikatów identyfikowanej przez *dwMsgMapID* w `CMessageMap` klasie pochodnej.

```
virtual BOOL ProcessWindowMessage(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```

### <a name="parameters"></a>Parametry

*Właściwość*<br/>
podczas Uchwyt do okna otrzymującego komunikat.

*uMsg*<br/>
podczas Wiadomość wysłana do okna.

*wParam*<br/>
podczas Dodatkowe informacje specyficzne dla wiadomości.

*lParam*<br/>
podczas Dodatkowe informacje specyficzne dla wiadomości.

*lResult*<br/>
określoną Wynik przetwarzania komunikatów.

*dwMsgMapID*<br/>
podczas Identyfikator mapy komunikatów, która będzie przetwarzać komunikat. Domyślna mapa komunikatów zadeklarowana za pomocą [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)jest identyfikowana przez 0. Alternatywna Mapa komunikatów zadeklarowana z [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)jest identyfikowana przez `msgMapID` .

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli komunikat jest w pełni obsługiwany. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywoływane przez procedurę okna obiektu [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) lub obiektu, który jest dynamicznie łańcucha do mapy komunikatów.

## <a name="see-also"></a>Zobacz też

[Klasa CDynamicChain](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
