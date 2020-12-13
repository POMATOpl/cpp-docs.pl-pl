---
description: 'Dowiedz się więcej na temat: Klasa CRichEditCntrItem'
title: Klasa CRichEditCntrItem
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 9e65e70a3fb03b65ebf9af7a619a5c4fbd3dba32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342963"
---
# <a name="cricheditcntritem-class"></a>Klasa CRichEditCntrItem

Funkcja [CRichEditView](../../mfc/reference/cricheditview-class.md) i [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)udostępnia funkcje kontrolki edycji wzbogaconej w kontekście architektury widoku dokumentu MFC.

## <a name="syntax"></a>Składnia

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Konstruuje `CRichEditCntrItem` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Aktywuje element jako inny typ.|

## <a name="remarks"></a>Uwagi

"Kontrolka edycji wzbogaconej" to okno, w którym użytkownik może wprowadzać i edytować tekst. Do tekstu może być przypisany znak i formatowanie akapitu, które mogą zawierać osadzone obiekty OLE. Formanty edycji wzbogaconej zapewniają interfejs programowania do formatowania tekstu. Jednak aplikacja musi zaimplementować wszelkie składniki interfejsu użytkownika niezbędne do udostępnienia użytkownikowi operacji formatowania.

`CRichEditView` Zachowuje cechę tekstu i formatowania tekstu. `CRichEditDoc` zachowuje listę elementów klienta OLE, które znajdują się w widoku. `CRichEditCntrItem` zapewnia dostęp po stronie kontenera do elementu klienta OLE.

Ten typowy formant systemu Windows (i w związku z tym [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) i powiązane klasy) jest dostępny tylko dla programów uruchomionych w systemach Windows 95/98 i Windows NT w wersji 3,51 i nowszych.

Przykład użycia zaawansowanej edycji elementów kontenera w aplikacji MFC można znaleźć w przykładowej aplikacji programu [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrich. h

## <a name="cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a> CRichEditCntrItem::CRichEditCntrItem

Wywołaj tę funkcję, aby utworzyć `CRichEditCntrItem` obiekt i dodać go do dokumentu kontenera.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parametry

*preo*<br/>
Wskaźnik na strukturę [ODobiektową](/windows/win32/api/richole/ns-richole-reobject) opisującą element OLE. Nowy `CRichEditCntrItem` obiekt jest zbudowany wokół tego elementu OLE. Jeśli *PREO* ma wartość null, element klienta jest pusty.

*Element pContainer*<br/>
Wskaźnik do dokumentu kontenera, który będzie zawierać ten element. Jeśli *element pContainer* ma wartość null, należy jawnie wywołać [COleDocument:: AddItem](../../mfc/reference/coledocument-class.md#additem) , aby dodać ten element klienta do dokumentu.

### <a name="remarks"></a>Uwagi

Ta funkcja nie wykonuje żadnych inicjalizacji OLE.

Aby uzyskać więcej informacji, zobacz strukturę [obiektów](/windows/win32/api/richole/ns-richole-reobject) w Windows SDK.

## <a name="cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a> CRichEditCntrItem::SyncToRichEditObject

Wywołaj tę funkcję, aby synchronizować aspekt urządzenia [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect), od tego `CRichEditCntrltem` do określonego przez *REO*.

```cpp
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parametry

*reo*<br/>
Odwołanie do struktury [obiektu](/windows/win32/api/richole/ns-richole-reobject) , która OPISUJE element OLE.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przykładowy program WORDPAD dla MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Klasa CRichEditView](../../mfc/reference/cricheditview-class.md)
