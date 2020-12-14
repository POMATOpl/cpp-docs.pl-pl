---
description: 'Dowiedz się więcej na temat: Klasa CSplitterWndEx'
title: Klasa CSplitterWndEx
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 357f650551871cc9768c8e4e693bd62bb5e69bc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345098"
---
# <a name="csplitterwndex-class"></a>Klasa CSplitterWndEx

Reprezentuje niestandardowe okno rozdzielacza.

## <a name="syntax"></a>Składnia

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Konstruktor domyślny.|
|`CSplitterWndEx::~CSplitterWndEx`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Wywoływane przez platformę, by narysować okno rozdzielacza. (Przesłania [CSplitterWnd:: OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Uwagi

Zastąp `OnDrawSplitter` metodę, aby dostosować wygląd składników graficznych okna rozdzielacza.

`CSplitterWndEx`Klasa jest używana razem z metodami [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)i [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) , które są implementowane przez program Visual Manager. Aby spowodować, że program Visual Manager rysuje okno rozdzielacza w aplikacji, Zastąp deklaracje klasy klasą `CSplitterWnd` `CSplitterWndEx` . W przypadku aplikacji okien ramowych Klasa okna rozdzielacza jest zadeklarowana w klasie CMainFrame, która znajduje się w MainFrm. h. Aby zapoznać się z przykładem, zobacz przykład `OutlookDemo` w katalogu Samples.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxsplitterwndex. h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a> CSplitterWndEx::OnDrawSplitter

Wywoływane przez platformę, by narysować okno rozdzielacza.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia. Jeśli ten parametr ma wartość NULL, struktura ponownie narysuje aktywne okno.

*Npowiadomienia*<br/>
podczas Jedna z `CSplitterWnd::ESplitType` wartości wyliczenia, która określa element okna rozdzielacza do rysowania. Prawidłowe wartości to `splitBox`, `splitBar`, `splitIntersection` i `splitBorder`.

*cinania*<br/>
podczas Prostokąt ograniczający, który określa wymiary i lokalizację do rysowania określonego elementu okna rozdzielacza.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../hierarchy-chart.md)<br/>
[Klasy](mfc-classes.md)<br/>
[Klasa CSplitterWnd](csplitterwnd-class.md)<br/>
[Klasa CMFCVisualManager](cmfcvisualmanager-class.md)
