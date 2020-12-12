---
description: 'Dowiedz się więcej na temat: Klasa CDocItem'
title: Klasa CDocItem
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 9e126d4351248165a3961739c13cc6ce7330c10c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185144"
---
# <a name="cdocitem-class"></a>Klasa CDocItem

Klasa bazowa dla elementów dokumentu, które są składnikami danych dokumentu.

## <a name="syntax"></a>Składnia

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDocItem:: GetDocument](#getdocument)|Zwraca dokument zawierający element.|
|[CDocItem:: ISBLANK](#isblank)|Określa, czy element zawiera wszystkie informacje.|

## <a name="remarks"></a>Uwagi

`CDocItem` obiekty służą do reprezentowania elementów OLE w dokumentach klienta i serwera.

Aby uzyskać więcej informacji, zobacz [kontenery artykułów: implementowanie kontenera](../../mfc/containers-implementing-a-container.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Afxole. h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a> CDocItem:: GetDocument

Wywołaj tę funkcję, aby pobrać dokument zawierający element.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do dokumentu zawierającego element; Wartość NULL, jeśli element nie jest częścią dokumentu.

### <a name="remarks"></a>Uwagi

Ta funkcja jest zastępowana w klasach pochodnych [COleClientItem](../../mfc/reference/coleclientitem-class.md) i [COleServerItem](../../mfc/reference/coleserveritem-class.md), zwracająca wskaźnik do obiektu [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)lub [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) .

## <a name="cdocitemisblank"></a><a name="isblank"></a> CDocItem:: ISBLANK

Wywoływane przez platformę, gdy występuje Serializacja domyślna.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli element nie zawiera żadnych informacji; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Domyślnie `CDocItem` obiekty nie są puste. Obiekty [COleClientItem](../../mfc/reference/coleclientitem-class.md) są czasami puste, ponieważ pochodzą bezpośrednio z programu `CDocItem` . Jednak obiekty [COleServerItem](../../mfc/reference/coleserveritem-class.md) są zawsze puste. Domyślnie aplikacje OLE zawierające `COleClientItem` obiekty, które nie mają zakresu x lub y, są serializowane. Jest to realizowane przez zwrócenie wartości TRUE z przesłonięcia, `IsBlank` gdy element nie ma zakresu x lub y.

Zastąp tę funkcję, jeśli chcesz zaimplementować inne akcje podczas serializacji.

## <a name="see-also"></a>Zobacz też

[Klasa CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Klasa COleServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Klasa COleClientItem](../../mfc/reference/coleclientitem-class.md)
