---
description: 'Dowiedz się więcej na temat: Klasa CMFCDragFrameImpl'
title: Klasa CMFCDragFrameImpl
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 9885b750ace86d11ca573f23c7ee1c03d8926921
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294057"
---
# <a name="cmfcdragframeimpl-class"></a>Klasa CMFCDragFrameImpl

`CMFCDragFrameImpl`Klasa rysuje prostokąt przeciągany, który pojawia się, gdy użytkownik przeciąga okienko w standardowym trybie dokowania.
Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>Uwagi

Obiekt tej klasy jest osadzony w każdym obiekcie [klasy CPane](../../mfc/reference/cpane-class.md) . W tym przypadku każde okienko używające `CanFloat` metody wyświetla prostokąt przeciągany, gdy użytkownik przeciągnie go.

Możesz kontrolować grubość prostokąta przeciągania przy użyciu [AFX_GLOBAL_DATA:: m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) i [AFX_GLOBAL_DATA:: m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdragframeimpl. h

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a> CMFCDragFrameImpl::EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>Parametry

podczas *bClearInternalRects*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdragframeimplinit"></a><a name="init"></a> CMFCDragFrameImpl:: init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>Parametry

podczas *pDraggedWnd*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a> CMFCDragFrameImpl::MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>Parametry

podczas *bForceMove*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a> CMFCDragFrameImpl::P laceTabPreDocking

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>Parametry

podczas *pTabbedBar*<br/>

podczas *bFirstTime*<br/>

podczas *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a> CMFCDragFrameImpl::RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>Parametry

podczas *pOldTargetBar*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a> CMFCDragFrameImpl:: elementu ResetState

```cpp
void ResetState();
```

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CPane](../../mfc/reference/cpane-class.md)
