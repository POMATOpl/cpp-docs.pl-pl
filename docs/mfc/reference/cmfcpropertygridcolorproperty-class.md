---
description: 'Dowiedz się więcej na temat: Klasa CMFCPropertyGridColorProperty'
title: Klasa CMFCPropertyGridColorProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 7673044a149dc1b5171167ed0854918434651dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334710"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>Klasa CMFCPropertyGridColorProperty

`CMFCPropertyGridColorProperty`Klasa obsługuje element formantu listy właściwości, który powoduje otwarcie okna dialogowego wyboru koloru.

## <a name="syntax"></a>Składnia

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Konstruuje `CMFCPropertyGridColorProperty` obiekt.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Włącza przycisk *automatyczny* w oknie dialogowym wyboru koloru. (Standardowy przycisk Automatyczny ma etykietę **automatyczną**).|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Włącza *inny* przycisk w oknie dialogowym wyboru koloru. (Inny przycisk standardowy ma etykietę **więcej kolorów**).|
|`CMFCPropertyGridColorProperty::FormatProperty`|Formatuje tekstową reprezentację wartości właściwości. (Przesłania [CMFCPropertyGridProperty:: FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridColorProperty:: GetColor](#getcolor)|Pobiera bieżący kolor właściwości.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Wywoływane przez platformę, gdy użytkownik kliknie przycisk znajdujący się w właściwości. (Przesłania [CMFCPropertyGridProperty:: OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Wywoływane przez platformę, aby wyświetlić wartość właściwości. (Przesłania [CMFCPropertyGridProperty:: OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|
|`CMFCPropertyGridColorProperty::OnEdit`|Wywoływane przez platformę, gdy użytkownik zamierza zmodyfikować wartość właściwości. (Przesłania [CMFCPropertyGridProperty:: onedit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit)).|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Wywoływane przez platformę, gdy wartość właściwości edytowanej została zmieniona. (Przesłania [CMFCPropertyGridProperty:: OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|
|[CMFCPropertyGridColorProperty:: SetColor](#setcolor)|Ustawia nowy kolor dla właściwości.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Określa liczbę kolumn w bieżącej siatce właściwości koloru.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Ustawia oryginalną wartość właściwości, którą można edytować.|

## <a name="remarks"></a>Uwagi

`CMFCPropertyGridColorProperty`Klasa obsługuje Właściwość koloru, którą można dodać do kontrolki listy właściwości. Aby uzyskać więcej informacji, zobacz [Klasa CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCPropertyGridColorProperty` klasy i konfigurowania tego obiektu przy użyciu różnych metod `CMFCPropertyGridColorProperty` klasy. Kod wyjaśnia, jak włączyć automatyczne i inne przyciski oraz jak ustawić kolor i liczbę kolumn. Ten przykład jest częścią [nowych kontrolek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxpropertygridctrl. h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a> CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty

Konstruuje `CMFCPropertyGridColorProperty` obiekt.

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>Parametry

*strName*<br/>
podczas Nazwa właściwości.

*Kolor*<br/>
podczas Wartość koloru właściwości.

*pPalette*<br/>
podczas Wskaźnik do palety kolorów. Wartość domyślna to NULL.

*lpszDescr*<br/>
podczas Opis właściwości. Wartość domyślna to NULL.

*dwData*<br/>
podczas Dane specyficzne dla aplikacji, takie jak liczba całkowita lub wskaźnik do innych danych, które są skojarzone z właściwością. Wartość domyślna to 0.

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCPropertyGridColorProperty::EnableAutomaticButton

Włącza przycisk *automatyczny* w oknie dialogowym wyboru koloru. (Standardowy przycisk Automatyczny ma etykietę **automatyczną**).

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Tekst etykiety przycisku automatycznego.

*colorAutomatic*<br/>
podczas Wartość koloru RGB domyślnego (domyślnego) koloru.

*bEnable*<br/>
podczas Wartość TRUE, aby włączyć przycisk Automatyczny; w przeciwnym razie FALSE. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a> CMFCPropertyGridColorProperty::EnableOtherButton

Włącza *inny* przycisk w oknie dialogowym wyboru koloru. (Inny przycisk standardowy ma etykietę **więcej kolorów**).

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Tekst etykiety drugiego przycisku.

*bAltColorDlg*<br/>
podczas Wartość TRUE powoduje wyświetlenie okna `CMFCColorDialog` dialogowego; Wartość FALSE, aby wyświetlić okno dialogowe wyboru koloru standardowego. Wartość domyślna to TRUE.

*bEnable*<br/>
podczas PRAWDA, aby wyświetlić drugi przycisk; w przeciwnym razie FALSE.  Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a> CMFCPropertyGridColorProperty:: GetColor

Pobiera bieżący kolor właściwości.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość koloru RGB.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a> CMFCPropertyGridColorProperty:: SetColor

Ustawia nowy kolor dla właściwości.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Wartość koloru RGB.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCPropertyGridColorProperty::SetColumnsNumber

Określa liczbę kolumn w bieżącej siatce właściwości koloru.

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Parametry

*nColumnsNumber*<br/>
podczas Preferowana liczba kolumn w siatce właściwości koloru.

### <a name="remarks"></a>Uwagi

Ta metoda ustawia wartość `m_nColumnsNumber` chronionego elementu członkowskiego danych.

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a> CMFCPropertyGridColorProperty::SetOriginalValue

Ustawia oryginalną wartość właściwości, którą można edytować.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Parametry

*varValue*<br/>
podczas Wartość.

### <a name="remarks"></a>Uwagi

Użyj metody [CMFCPropertyGridProperty:: ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) , aby zresetować oryginalną wartość edytowanej właściwości.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Klasa CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
