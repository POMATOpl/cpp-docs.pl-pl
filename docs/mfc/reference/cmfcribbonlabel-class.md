---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonLabel'
title: Klasa CMFCRibbonLabel
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: 0699e76dfe90b87cd813d18d076adf23f8512bee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321829"
---
# <a name="cmfcribbonlabel-class"></a>Klasa CMFCRibbonLabel

Implementuje nieklikniętą etykietę tekstową dla wstążki.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Konstruuje i inicjuje `CMFCRibbonLabel` obiekt z określonym ciągiem tekstowym.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|`CMFCRibbonLabel::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Określa dane ułatwień dostępu dla bieżącego elementu etykiety wstążki. (Przesłania [CMFCRibbonButton:: SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Uwagi

Po utworzeniu etykiety wstążki Dodaj ją do panelu przez wywołanie [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

Nie można dodać etykiety wstążki do paska narzędzi Szybki dostęp.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonLabel. h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a> CMFCRibbonLabel::CMFCRibbonLabel

Tworzy i inicjuje obiekt [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) , który wyświetla określony ciąg tekstowy.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Parametry

*lpszText*<br/>
podczas Tekst, który ma być wyświetlany w etykiecie.

*bIsMultiLine*<br/>
podczas PRAWDA, aby określić, że etykieta jest etykieta wielowierszowa; w przeciwnym razie FALSE.

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonLabel::SetACCData

Określa dane ułatwień dostępu dla bieżącego elementu etykiety wstążki.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametry

*pParent*<br/>
podczas Reprezentuje okno nadrzędne bieżącej etykiety wstążki.

*data*<br/>
określoną Obiekt typu `CAccessibilityData` , który jest wypełniony danymi dostępności bieżącej etykiety wstążki.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli parametr *danych* został pomyślnie wypełniony danymi dostępności bieżącej etykiety wstążki; w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
