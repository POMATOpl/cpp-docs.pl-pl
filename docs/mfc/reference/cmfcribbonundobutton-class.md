---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonUndoButton'
title: Klasa CMFCRibbonUndoButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 8bfc02b61160a5f11a6913736c5dc784c4d00ce4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264937"
---
# <a name="cmfcribbonundobutton-class"></a>Klasa CMFCRibbonUndoButton

`CMFCRibbonUndoButton`Klasa implementuje przycisk listy rozwijanej, który zawiera najnowsze polecenia użytkownika. Użytkownicy mogą wybrać jedno lub więcej z najnowszych poleceń z listy rozwijanej, aby wykonać je ponownie lub cofnąć.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Tworzy nowy `CMFCRibbonUndoButton` Obiekt przy użyciu określonego identyfikatora polecenia, etykiety tekstowej i obrazów z listy obrazów obiektu nadrzędnego.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Dodaje nową akcję do listy akcji.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Czyści listę akcji, która jest listą rozwijaną.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Określa liczbę elementów wybranych przez użytkownika z listy rozwijanej.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Wskazuje, czy obiekt zawiera menu.|

## <a name="remarks"></a>Uwagi

`CMFCRibbonUndoButton`Klasa używa stosu, aby reprezentować listę rozwijaną.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCRibbonUndoButton` klasy i Dodawanie nowej akcji do listy akcji. Ten fragment kodu jest częścią [przykładu gadżetów wstążki](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonundobutton. h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a> CMFCRibbonUndoButton::AddUndoAction

Dodaje nową akcję do listy akcji.

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Etykieta akcji, która będzie wyświetlana na liście rozwijanej.

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a> CMFCRibbonUndoButton::CleanUpUndoList

Czyści listę akcji, która jest listą rozwijaną.

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a> CMFCRibbonUndoButton::CMFCRibbonUndoButton

Tworzy nowy `CMFCRibbonUndoButton` Obiekt przy użyciu określonego identyfikatora polecenia, etykiety tekstowej i obrazów z listy obrazów obiektu nadrzędnego.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>Parametry

*nID*<br/>
podczas Określa identyfikator polecenia.

*lpszText*<br/>
podczas Określa etykietę tekstu przycisku.

*nSmallImageIndex*<br/>
podczas Indeks (liczony od zera) na liście obrazów obiektu nadrzędnego dla małego obrazu przycisku.

*nLargeImageIndex*<br/>
podczas Indeks (liczony od zera) na liście obrazów obiektu nadrzędnego dla dużego obrazu przycisku.

*hIcon*<br/>
podczas Uchwyt do ikony, której można użyć jako obrazu przycisku.

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a> CMFCRibbonUndoButton::GetActionNumber

Określa liczbę elementów wybranych przez użytkownika z listy rozwijanej.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów wybranych przez użytkownika.

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a> CMFCRibbonUndoButton::HasMenu

Wskazuje, czy obiekt zawiera menu.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[Klasa CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
