---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonContextCaption'
title: Klasa CMFCRibbonContextCaption
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: fa4134b89055274e4f44bef1150518207e06143e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293628"
---
# <a name="cmfcribboncontextcaption-class"></a>Klasa CMFCRibbonContextCaption

Implementuje kolorowy podpis wyświetlany w górnej części kategorii wstążki lub kategorii kontekstowej.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|[CMFCRibbonContextCaption:: GetColor](#getcolor)|Zwraca kolor podpisu.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|

## <a name="remarks"></a>Uwagi

Nie można bezpośrednio utworzyć wystąpienia tej klasy. Klasa [klasy CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) używa tej klasy wewnętrznie do dodawania koloru do kategorii wstążki.

Aby ustawić kolor dla kategorii wstążki, wywołaj [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Aby ustawić kolor dla kategorii kontekstowych, wywołaj [CMFCRibbonBar:: AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonBar. h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a> CMFCRibbonContextCaption:: GetColor

Zwraca kolor tła podpisu.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwracana wartość może być jedną z następujących wartości wyliczanych:

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Uwagi

Kolor podpisu można ustawić przez wywołanie [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) lub [CMFCRibbonBar:: AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a> CMFCRibbonContextCaption::GetRightTabX

Pobiera pozycję prawej krawędzi karty wstążki kategorii.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca prawą ręką wartość X otaczającego prostokąta `CMFCRibbonCategory` karty wstążki obiektu lub wartość-1, jeśli karta została obcięta.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Klasa CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
