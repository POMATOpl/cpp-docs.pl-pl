---
description: 'Dowiedz się więcej na temat: Klasa CDynamicChain'
title: Klasa CDynamicChain
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 5ada99b519900150afa2143fb1527245797fed98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141820"
---
# <a name="cdynamicchain-class"></a>Klasa CDynamicChain

Ta klasa udostępnia metody obsługujące dynamiczny łańcuch map komunikatów.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CDynamicChain
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Konstruktor.|
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDynamicChain::CallChain](#callchain)|Kieruje komunikat systemu Windows do mapy komunikatów innego obiektu.|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Usuwa wpis mapy komunikatów z kolekcji.|
|[CDynamicChain::SetChainEntry](#setchainentry)|Dodaje wpis mapy komunikatów do kolekcji lub modyfikuje istniejący wpis.|

## <a name="remarks"></a>Uwagi

`CDynamicChain` zarządza kolekcją map komunikatów, umożliwiając kierowanie komunikatów systemu Windows w czasie wykonywania do mapy komunikatów innego obiektu.

Aby dodać obsługę dynamicznego łańcucha map komunikatów, wykonaj następujące czynności:

- Utwórz klasę z `CDynamicChain` . Na mapie wiadomości Określ makro [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) , które ma być powiązane z domyślną mapą wiadomości innego obiektu.

- Pochodna każdej klasy, do której chcesz utworzyć łańcuch, z [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap` umożliwia obiektowi uwidocznienie map komunikatów na innych obiektach.

- Wywołaj, `CDynamicChain::SetChainEntry` Aby zidentyfikować obiekt i mapę wiadomości, do której chcesz utworzyć łańcuch.

Załóżmy na przykład, że klasa została zdefiniowana w następujący sposób:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

Klient następnie wywołuje `CMyWindow::SetChainEntry` :

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

gdzie `chainedObj` jest obiektem łańcuchowym i jest wystąpieniem klasy pochodzącej od `CMessageMap` . Teraz, jeśli `myCtl` odbiera komunikat, który nie jest obsługiwany przez `OnPaint` `OnSetFocus` program lub, procedura okna kieruje komunikat do `chainedObj` domyślnej mapy komunikatów.

Aby uzyskać więcej informacji na temat łańcucha mapy komunikatów, zobacz [mapy komunikatów](../../atl/message-maps-atl.md) w artykule "klasy biblioteki ATL".

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a> CDynamicChain::CallChain

Kieruje komunikat systemu Windows do mapy komunikatów innego obiektu.

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>Parametry

*dwChainID*<br/>
podczas Unikatowy identyfikator skojarzony z łańcuchowym obiektem i jego mapą komunikatów.

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

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli komunikat jest w pełni przetwarzany; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Aby można było wywołać procedurę okna `CallChain` , należy określić makro [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) w mapie wiadomości. Aby zapoznać się z przykładem, zobacz Omówienie [CDynamicChain](../../atl/reference/cdynamicchain-class.md) .

`CallChain` wymaga wcześniejszego wywołania [SetChainEntry](#setchainentry) , aby skojarzyć wartość *dwChainID* z obiektem i jego mapą komunikatów.

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a> CDynamicChain::CDynamicChain

Konstruktor.

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a> CDynamicChain:: ~ CDynamicChain

Destruktor.

```
~CDynamicChain();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a> CDynamicChain::RemoveChainEntry

Usuwa określoną mapę wiadomości z kolekcji.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Parametry

*dwChainID*<br/>
podczas Unikatowy identyfikator skojarzony z łańcuchowym obiektem i jego mapą komunikatów. Ta wartość została pierwotnie zdefiniowana przez wywołanie [SetChainEntry](#setchainentry).

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli mapa komunikatów została pomyślnie usunięta z kolekcji. W przeciwnym razie FALSE.

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a> CDynamicChain::SetChainEntry

Dodaje określoną mapę wiadomości do kolekcji.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Parametry

*dwChainID*<br/>
podczas Unikatowy identyfikator skojarzony z łańcuchowym obiektem i jego mapą komunikatów.

*pObject*<br/>
podczas Wskaźnik do obiektu łańcucha deklarującego mapę komunikatów. Ten obiekt musi pochodzić od [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
podczas Identyfikator mapy wiadomości w łańcuchowym obiekcie. Wartość domyślna to 0, która identyfikuje domyślną mapę wiadomości zadeklarowaną z [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Aby określić alternatywną mapę komunikatów zadeklarowaną z [ALT_MSG_MAP (msgMapID)](message-map-macros-atl.md#alt_msg_map), Przekaż `msgMapID` .

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli mapa komunikatów została pomyślnie dodana do kolekcji. W przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Jeśli wartość *dwChainID* już istnieje w kolekcji, jej skojarzony obiekt i mapa komunikatów są zastępowane odpowiednio przez *pObject* i *dwMsgMapID*. W przeciwnym razie zostanie dodany nowy wpis.

## <a name="see-also"></a>Zobacz też

[Klasa CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
