---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonMainPanel'
title: Klasa CMFCRibbonMainPanel
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 823a1ce8a8684ca791f838346a1fb50727096a62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321815"
---
# <a name="cmfcribbonmainpanel-class"></a>Klasa CMFCRibbonMainPanel

Implementuje panel wstążki, który jest wyświetlany po kliknięciu [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).

## <a name="syntax"></a>Składnia

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Konstruktor domyślny.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonMainPanel:: Add](#add)|Dodaje element wstążki do lewego okienka panelu przycisku aplikacji. (Przesłania [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Dodaje ciąg tekstowy do menu listy ostatnio używanych plików.|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Dodaje element wstążki do dolnego okienka panelu aplikacji wstążki.|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Dodaje element wstążki do prawego okienka panelu przycisku aplikacji.|
|`CMFCRibbonMainPanel::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Zwraca prostokąt, który reprezentuje obszar głównego panelu wstążki.|
|`CMFCRibbonMainPanel::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|

## <a name="remarks"></a>Uwagi

Struktura zostanie wyświetlona `CMFCRibbonMainPanel` po otwarciu panelu aplikacji. Zawiera trzy okienka:

- Okienko po lewej stronie zawiera polecenia skojarzone z plikami, takie jak **Otwórz**, **Zapisz**, **Drukuj** i **Zamknij**. Aby dodać polecenie do tego okienka, wywołaj [CMFCRibbonMainPanel:: Add](#add).

- Prawe okienko zawiera opcje modyfikujące polecenie kliknięte w okienku po lewej stronie. Jeśli na przykład klikniesz pozycję **Zapisz jako** w okienku po lewej stronie, w okienku po prawej stronie będzie można wyświetlić dostępne typy plików. Aby dodać element do tego okienka, wywołaj [CMFCRibbonMainPanel:: AddToRight](#addtoright).

- Dolne okienko zawiera przyciski umożliwiające zmianę ustawień aplikacji i wyjście z programu. Aby dodać element do tego okienka, wywołaj [CMFCRibbonMainPanel:: AddToBottom](#addtobottom).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonMainPanel. h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a> CMFCRibbonMainPanel:: Add

Dodaje element wstążki do lewego okienka panelu przycisku aplikacji.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>Parametry

*pElem*<br/>
[in. out] Wskaźnik do elementu wstążki, który ma zostać dodany do panelu głównego.

### <a name="remarks"></a>Uwagi

Dodaje element wstążki do panelu. Elementy dodane przy użyciu tej metody będą znajdować się w lewej kolumnie panelu głównego.

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a> CMFCRibbonMainPanel::AddRecentFilesList

Dodaje ciąg tekstowy do menu listy ostatnio używanych plików.

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
Określa ciąg, który ma zostać dodany do listy ostatnio używanych plików.

*nWidth*<br/>
Określa szerokość (w pikselach) panelu listy ostatnio używanych plików.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a> CMFCRibbonMainPanel::AddToBottom

Dodaje element wstążki do dolnego okienka panelu aplikacji wstążki.

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>Parametry

*pElem*<br/>
[in. out] Wskaźnik do elementu wstążki, który ma zostać dodany do dolnej części panelu głównego.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a> CMFCRibbonMainPanel::AddToRight

Dodaje element wstążki do prawego okienka panelu przycisku aplikacji.

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>Parametry

*pElem*<br/>
Wskaźnik do elementu wstążki, który ma zostać dodany po prawej stronie panelu głównego.

*nWidth*<br/>
Określa szerokość (w pikselach) prawego panelu.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby dodać element wstążki do prawego panelu. Prawy panel zazwyczaj wyświetla listę ostatnio używanych plików, ale można dodać każdy inny element wstążki tutaj.

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a> CMFCRibbonMainPanel::GetCommandsFrame

Zwraca prostokąt, który reprezentuje obszar głównego panelu wstążki.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Wartość zwracana

Prostokąt, który reprezentuje obszar głównego panelu wstążki.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
