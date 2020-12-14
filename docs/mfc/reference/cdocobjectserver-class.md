---
description: 'Dowiedz się więcej na temat: Klasa CDocObjectServer'
title: Klasa CDocObjectServer
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: 5a87363fef66a4819fc8efd504da96398cf3c89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184949"
---
# <a name="cdocobjectserver-class"></a>Klasa CDocObjectServer

Implementuje dodatkowe interfejsy OLE, które są konieczne do przepełnienia normalnego `COleDocument` serwera na pełny serwer DocObject: `IOleDocument` , `IOleDocumentView` , `IOleCommandTarget` , i `IPrint` .

## <a name="syntax"></a>Składnia

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Konstruuje `CDocObjectServer` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Aktywuje serwer obiektów dokumentów, ale go nie pokazuje.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CDocObjectServer:: OnActivateView](#onactivateview)|Wyświetla widok DocObject.|
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Przywraca stan widoku DocObject.|
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Zapisuje stan widoku DocObject.|

## <a name="remarks"></a>Uwagi

`CDocObjectServer` jest pochodną `CCmdTarget` i współpracuje ściśle z, `COleServerDoc` Aby uwidocznić interfejsy.

Dokument serwera DocObject może zawierać obiekty [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) , które reprezentują interfejs serwera do DocObject elementów.

Aby dostosować serwer DocObject, należy utworzyć własną klasę z `CDocObjectServer` i zastąpić jej funkcje konfiguracji widoku, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate)i [OnSaveViewState](#onsaveviewstate). Musisz podać nowe wystąpienie klasy w odpowiedzi na wywołania struktury.

Aby uzyskać więcej informacji na temat DocObjects, zobacz [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) i [COleCmdUI](../../mfc/reference/colecmdui-class.md) w *dokumentacji MFC*.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdocob. h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a> CDocObjectServer::ActivateDocObject

Wywołaj tę funkcję, aby aktywować (ale nie pokazywać) serwer obiektów dokumentów.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Uwagi

`ActivateDocObject` wywołuje `IOleDocumentSite` `ActivateMe` metodę, ale nie wyświetla widoku, ponieważ oczekuje na szczegółowe instrukcje dotyczące sposobu konfigurowania i wyświetlania widoku, nadane w wywołaniu [CDocObjectServer:: OnActivateView](#onactivateview).

Ze sobą `ActivateDocObject` i `OnActivateView` Uaktywniaj i wyświetlaj widok DocObject. Aktywacja DocObject różni się od innych rodzajów aktywacji OLE w miejscu. Aktywacja DocObject pomija wyświetlanie obramowania kreskowania w miejscu i wypełnień obiektów (takich jak uchwyty zmiany rozmiaru), ignoruje funkcje zakresu obiektów i rysuje paski przewijania w prostokącie widoku zamiast rysowania ich poza tym prostokątem (jak w przypadku normalnej aktywacji w miejscu).

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a> CDocObjectServer::CDocObjectServer

Konstruuje i inicjuje `CDocObjectServer` obiekt.

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>Parametry

*pOwner*<br/>
Wskaźnik do dokumentu lokacji klienta, który jest klientem serwera DocObject.

*pDocSite*<br/>
Wskaźnik do `IOleDocumentSite` interfejsu zaimplementowanego przez kontener.

### <a name="remarks"></a>Uwagi

Gdy DocObject jest aktywny, interfejs OLE lokacji klienta ( `IOleDocumentSite` ) umożliwia serwerowi DocObject komunikowanie się z klientem (kontenerem). Gdy serwer DocObject jest aktywowany, najpierw sprawdza, czy kontener implementuje `IOleDocumentSite` interfejs. Jeśli tak, [COleServerDoc:: GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) jest wywoływana w celu sprawdzenia, czy kontener obsługuje DocObjects. Domyślnie `GetDocObjectServer` zwraca wartość null. Należy przesłonić `COleServerDoc::GetDocObjectServer` , aby utworzyć nowy `CDocObjectServer` obiekt lub obiekt pochodny, ze wskaźnikami do `COleServerDoc` kontenera i jego `IOleDocumentSite` interfejs jako argumenty do konstruktora.

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a> CDocObjectServer:: OnActivateView

Wywołaj tę funkcję, aby wyświetlić widok DocObject.

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość błędu lub ostrzeżenia. Domyślnie zwraca NOERROR, jeśli pomyślne; w przeciwnym razie E_FAIL.

### <a name="remarks"></a>Uwagi

Ta funkcja tworzy okno ramowe w miejscu, rysuje paski przewijania w widoku, konfiguruje menu, które są współużytkowane przez serwer, dodaje kontrolki ramki, ustawia aktywny obiekt, a następnie wyświetla okno ramki w miejscu i ustawia fokus.

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a> CDocObjectServer::OnApplyViewState

Przesłoń tę funkcję, aby przywrócić stan widoku DocObject.

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametry

*ty*<br/>
`CArchive`Obiekt, z którego ma zostać Zserializowany stan widoku.

### <a name="remarks"></a>Uwagi

Ta funkcja jest wywoływana, gdy widok jest wyświetlany po raz pierwszy po utworzeniu wystąpienia. `OnApplyViewState` powoduje, że widok umożliwia ponowne zainicjowanie samego siebie zgodnie z danymi w `CArchive` obiekcie wcześniej zapisywanych za pomocą [OnSaveViewState](#onsaveviewstate). Widok musi sprawdzać poprawność danych w `CArchive` obiekcie, ponieważ kontener nie próbuje zinterpretować danych stanu widoku w dowolny sposób.

Programu można użyć `OnSaveViewState` do przechowywania informacji trwałych specyficznych dla stanu widoku. Jeśli przesłonisz `OnSaveViewState` przechowywanie informacji, chcesz przesłonić, `OnApplyViewState` Aby odczytać te informacje i zastosować je do widoku, gdy zostanie on nowo aktywowany.

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a> CDocObjectServer::OnSaveViewState

Zastąp tę funkcję, aby zapisać dodatkowe informacje o stanie na potrzeby widoku DocObject.

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametry

*ty*<br/>
`CArchive`Obiekt, do którego jest serializowany stan widoku.

### <a name="remarks"></a>Uwagi

Twój stan może zawierać właściwości, takie jak typ widoku, współczynnik powiększenia, punkt wstawiania i punkt zaznaczenia itd. Kontener zazwyczaj wywołuje tę funkcję przed zdezaktywowaniem widoku. Zapisany stan można później przywrócić za pomocą [OnApplyViewState](#onapplyviewstate).

Programu można użyć `OnSaveViewState` do przechowywania informacji trwałych specyficznych dla stanu widoku. Jeśli przesłonisz `OnSaveViewState` przechowywanie informacji, chcesz przesłonić, `OnApplyViewState` Aby odczytać te informacje i zastosować je do widoku, gdy zostanie on nowo aktywowany.

## <a name="see-also"></a>Zobacz też

[Klasa CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
