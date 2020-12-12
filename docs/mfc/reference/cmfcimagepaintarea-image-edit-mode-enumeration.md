---
description: 'Dowiedz się więcej o: CMFCImagePaintArea:: IMAGE_EDIT_MODE Enumeration'
title: CMFCImagePaintArea::IMAGE_EDIT_MODE — Wyliczenie
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: f28880d108be8fb4f2b14ede1a3cbd3c7dac9f2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265327"
---
# <a name="cmfcimagepaintareaimage_edit_mode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE — Wyliczenie

Określa tryb rysowania używany do modyfikowania obrazu w oknie dialogowym Edytor obrazów.

## <a name="syntax"></a>Składnia

```
enum IMAGE_EDIT_MODE
{
    IMAGE_EDIT_MODE_PEN = 0,
    IMAGE_EDIT_MODE_FILL,
    IMAGE_EDIT_MODE_LINE,
    IMAGE_EDIT_MODE_RECT,
    IMAGE_EDIT_MODE_ELLIPSE,
    IMAGE_EDIT_MODE_COLOR
};
```

## <a name="members"></a>Elementy członkowskie

|Nazwa|Opis|
|-|-|
|IMAGE_EDIT_MODE_PEN|Służy do rysowania pojedynczych pikseli.|
|IMAGE_EDIT_MODE_FILL|Służy do wypełniania wszystkich obszarów sąsiednich, które zawierają kolor w bieżącej lokalizacji kursora.|
|IMAGE_EDIT_MODE_LINE|Służy do rysowania linii.|
|IMAGE_EDIT_MODE_RECT|Służy do rysowania prostokąta.|
|IMAGE_EDIT_MODE_ELLIPSE|Służy do rysowania elipsy.|
|IMAGE_EDIT_MODE_COLOR|Służy do ustawiania kolor bieżącego koloru na bieżącej lokalizacji kursora.|

### <a name="remarks"></a>Uwagi

`CMFCImagePaintArea`Klasy i `CMFCImageEditorDialog` używają tego wyliczenia do ustawiania bieżącego trybu rysowania. Tryb rysowania i bieżący kolor są używane do modyfikowania obszaru obrazu w oknie dialogowym Edytor obrazów. Aby uzyskać więcej informacji na temat `CMFCImagePaintArea` i `CMFCImageEditorDialog` , zobacz Klasa [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md) i [Klasa CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md).

Po wybraniu koloru z obrazu przy użyciu trybu rysowania IMAGE_EDIT_MODE_COLOR, struktura ustawia bieżący tryb rysowania na IMAGE_EDIT_MODE_PEN.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afximagepaintarea. h

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[Klasa CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
