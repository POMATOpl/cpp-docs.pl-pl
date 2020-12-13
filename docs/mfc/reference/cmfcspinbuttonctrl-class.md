---
description: 'Dowiedz się więcej na temat: Klasa CMFCSpinButtonCtrl'
title: Klasa CMFCSpinButtonCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 87e9abc94247416704ab801beeaa1953c4cceb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339640"
---
# <a name="cmfcspinbuttonctrl-class"></a>Klasa CMFCSpinButtonCtrl

`CMFCSpinButtonCtrl`Klasa obsługuje Menedżera wizualizacji, który rysuje kontrolkę przycisku pokrętła.

## <a name="syntax"></a>Składnia

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Konstruktor domyślny.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCSpinButtonCtrl:: OnDraw](#ondraw)|Odmaluje bieżącą kontrolkę przycisk pokrętła.|

## <a name="remarks"></a>Uwagi

Aby użyć Menedżera wizualizacji do rysowania kontrolki przycisku pokrętła w aplikacji, Zastąp wszystkie wystąpienia klasy klasą `CSpinButtonCtrl` `CMFCSpinButtonCtrl` .

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób tworzenia obiektu `CMFCSpinButtonCtrl` klasy i używania jej `Create` metody.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Korzystanie CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxspinbuttonctrl. h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a> CMFCSpinButtonCtrl:: OnDraw

Odmaluje bieżącą kontrolkę przycisk pokrętła.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

### <a name="remarks"></a>Uwagi

Struktura wywołuje metodę w `CMFCSpinButtonCtrl::OnPaint` celu obsługi komunikatu [CWnd:: OnPaint](../../mfc/reference/cwnd-class.md#onpaint) i ta metoda z kolei wywołuje tę `CMFCSpinButtonCtrl::OnDraw` metodę. Zastąp tę metodę, aby dostosować sposób rysowania kontrolki przycisku pokrętła przez strukturę.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)
