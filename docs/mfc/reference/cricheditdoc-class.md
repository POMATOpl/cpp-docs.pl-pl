---
description: 'Dowiedz się więcej na temat: Klasa CRichEditDoc'
title: Klasa CRichEditDoc
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: 5e94fb8edb3f5a596b71ddd55cdcb2077ba6201d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342933"
---
# <a name="cricheditdoc-class"></a>Klasa CRichEditDoc

Funkcja [CRichEditView](../../mfc/reference/cricheditview-class.md) i [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)udostępnia funkcje kontrolki edycji wzbogaconej w kontekście architektury widoku dokumentu MFC.

## <a name="syntax"></a>Składnia

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRichEditDoc:: CreateClientItem](#createclientitem)|Wywołuje się, by wykonać czyszczenie dokumentu.|
|[CRichEditDoc:: GetStreamFormat](#getstreamformat)|Wskazuje, czy dane wejściowe i wyjściowe strumienia powinny zawierać informacje o formatowaniu.|
|[CRichEditDoc:: GetView](#getview)|Pobiera obiekt asssociated [CRichEditView](../../mfc/reference/cricheditview-class.md) .|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CRichEditDoc:: m_bRTF](#m_brtf)|Wskazuje, czy strumień operacji we/wy powinien zawierać formatowanie.|

## <a name="remarks"></a>Uwagi

"Kontrolka edycji wzbogaconej" to okno, w którym użytkownik może wprowadzać i edytować tekst. Do tekstu może być przypisany znak i formatowanie akapitu, które mogą zawierać osadzone obiekty OLE. Formanty edycji wzbogaconej zapewniają interfejs programowania do formatowania tekstu. Jednak aplikacja musi zaimplementować wszelkie składniki interfejsu użytkownika niezbędne do udostępnienia użytkownikowi operacji formatowania.

`CRichEditView` Zachowuje cechę tekstu i formatowania tekstu. `CRichEditDoc` zachowuje listę elementów klienta, które znajdują się w widoku. `CRichEditCntrItem` zapewnia dostęp po stronie kontenera do elementów klienta OLE.

Ten typowy formant systemu Windows (i w związku z tym [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) i powiązane klasy) jest dostępny tylko dla programów uruchomionych w systemach Windows 95/98 i Windows NT w wersji 3,51 i nowszych.

Przykład użycia zaawansowanego dokumentu edycji w aplikacji MFC można znaleźć w przykładowej aplikacji programu [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrich. h

## <a name="cricheditdoccreateclientitem"></a><a name="createclientitem"></a> CRichEditDoc:: CreateClientItem

Wywołaj tę funkcję, aby utworzyć `CRichEditCntrItem` obiekt i dodać go do tego dokumentu.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parametry

*preo*<br/>
Wskaźnik na strukturę [ODobiektową](/windows/win32/api/richole/ns-richole-reobject) opisującą element OLE. Nowy `CRichEditCntrItem` obiekt jest zbudowany wokół tego elementu OLE. Jeśli *PREO* ma wartość null, nowy element klienta jest pusty.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do nowego obiektu [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) , który został dodany do tego dokumentu.

### <a name="remarks"></a>Uwagi

Ta funkcja nie wykonuje żadnych inicjalizacji OLE.

Aby uzyskać więcej informacji, zobacz strukturę [obiektów](/windows/win32/api/richole/ns-richole-reobject) w Windows SDK.

## <a name="cricheditdocgetstreamformat"></a><a name="getstreamformat"></a> CRichEditDoc:: GetStreamFormat

Wywołaj tę funkcję, aby określić format tekstu służący do przesyłania strumieniowego zawartości wzbogaconej edycji.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Wartość zwracana

Jedna z następujących flag:

- SF_TEXT wskazuje, że formant edycji wzbogaconej nie utrzymuje informacji o formatowaniu.

- SF_RTF wskazuje, że formant edycji wzbogaconej zachowuje informacje o formatowaniu.

### <a name="remarks"></a>Uwagi

Wartość zwracana jest oparta na elemencie członkowskim danych [m_bRTF](#m_brtf) . Ta funkcja zwraca SF_RTF `m_bRTF` , jeśli ma wartość true; w przeciwnym razie SF_TEXT.

## <a name="cricheditdocgetview"></a><a name="getview"></a> CRichEditDoc:: GetView

Wywołaj tę funkcję, aby uzyskać dostęp do obiektu [CRichEditView](../../mfc/reference/cricheditview-class.md) skojarzonego z tym `CRichEditDoc` obiektem.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CRichEditView` obiektu skojarzonego z dokumentem.

### <a name="remarks"></a>Uwagi

Informacje o tekstach i formatowaniu są zawarte w `CRichEditView` obiekcie. `CRichEditDoc`Obiekt przechowuje elementy OLE do serializacji. Dla każdego z nich powinna istnieć tylko jedna z nich `CRichEditView` `CRichEditDoc` .

## <a name="cricheditdocm_brtf"></a><a name="m_brtf"></a> CRichEditDoc:: m_bRTF

Gdy ma wartość TRUE, wskazuje, że [CRichEditCtrl:: Streamer](../../mfc/reference/cricheditctrl-class.md#streamin) i [CRichEditCtrl:: StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) powinny przechowywać charakterystyki formatowania akapitu i znaku.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Zobacz też

[Przykładowy program WORDPAD dla MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CRichEditView](../../mfc/reference/cricheditview-class.md)<br/>
[Klasa CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)<br/>
[Klasa COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Klasa CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)
