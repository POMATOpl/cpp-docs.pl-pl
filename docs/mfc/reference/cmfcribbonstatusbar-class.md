---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonStatusBar'
title: Klasa CMFCRibbonStatusBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: 01436d535b410fd4a6c70f52760908e3547b7af8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265002"
---
# <a name="cmfcribbonstatusbar-class"></a>Klasa CMFCRibbonStatusBar

`CMFCRibbonStatusBar`Klasa implementuje formant paska stanu, który może wyświetlać elementy wstążki.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonStatusBar:: adddynamicelement](#adddynamicelement)|Dodaje element dynamiczny do paska stanu wstążki.|
|[CMFCRibbonStatusBar:: AddElement](#addelement)|Dodaje nowy element wstążki do paska stanu wstążki.|
|[CMFCRibbonStatusBar:: addextendedelement](#addextendedelement)|Dodaje element wstążki do rozszerzonego obszaru paska stanu wstążki.|
|[CMFCRibbonStatusBar:: AddSeparator](#addseparator)|Dodaje separator do paska stanu wstążki.|
|[CMFCRibbonStatusBar:: Create](#create)|Tworzy pasek stanu wstążki.|
|[CMFCRibbonStatusBar::CreateEx](#createex)|Tworzy pasek stanu wstążki z rozszerzonym stylem.|
|[CMFCRibbonStatusBar::FindByID](#findbyid)||
|[CMFCRibbonStatusBar:: FindElement](#findelement)|Zwraca wskaźnik do elementu, który ma określony identyfikator polecenia.|
|[CMFCRibbonStatusBar:: GetCount](#getcount)|Zwraca liczbę elementów, które znajdują się w głównym obszarze paska stanu wstążki.|
|[CMFCRibbonStatusBar:: GetElement](#getelement)|Zwraca wskaźnik do elementu, który znajduje się w określonym indeksie.|
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Zwraca liczbę elementów, które znajdują się w rozszerzonym obszarze paska stanu wstążki.|
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Zwraca wskaźnik do elementu, który znajduje się w określonym indeksie w rozszerzonym obszarze paska stanu wstążki.|
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCRibbonStatusBar:: getspace](#getspace)||
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||
|[CMFCRibbonStatusBar:: isextendedelement](#isextendedelement)||
|[CMFCRibbonStatusBar:: isinformationmode](#isinformationmode)|Określa, czy tryb informacji jest włączony dla paska stanu wstążki.|
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Przesłania [CMFCRibbonBar:: RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|
|[CMFCRibbonStatusBar::](#removeall)|Usuwa wszystkie elementy z paska stanu wstążki.|
|[CMFCRibbonStatusBar:: RemoveElement](#removeelement)|Usuwa element z określonym IDENTYFIKATORem polecenia z paska stanu wstążki.|
|[CMFCRibbonStatusBar:: SetInformation](#setinformation)|Włącza lub wyłącza tryb informacji dla paska stanu wstążki.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Wyświetla ciąg informacji, który pojawia się na pasku stanu wstążki, gdy jest włączony tryb informacji.|

## <a name="remarks"></a>Uwagi

Użytkownicy mogą zmieniać widoczność elementów wstążki na pasku stanu wstążki przy użyciu wbudowanego menu kontekstowego paska stanu wstążki. Elementy można dodawać i usuwać dynamicznie.

Pasek stanu wstążki ma dwa obszary: obszar główny i rozszerzony obszar. Rozszerzony obszar jest wyświetlany po prawej stronie paska stanu wstążki i pojawia się w innym kolorze niż obszar główny.

Zazwyczaj w głównym obszarze paska stanu są wyświetlane powiadomienia o stanie, a w obszarze rozszerzonym są wyświetlane kontrolki widoku. Rozszerzony obszar pozostanie widoczny tak długo, jak to możliwe, gdy użytkownik zmienia rozmiar paska stanu wstążki.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonStatusBar` klasie. W przykładzie pokazano, jak dodać nowy element wstążki do paska stanu wstążki, dodać element wstążki do rozszerzonego obszaru paska stanu wstążki, dodać separator i włączyć tryb normalny dla paska stanu wstążki.

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonstatusbar. h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a> CMFCRibbonStatusBar:: adddynamicelement

Dodaje element dynamiczny do paska stanu wstążki.

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>Parametry

*pElement*<br/>
podczas Wskaźnik do elementu dynamicznego.

### <a name="remarks"></a>Uwagi

W przeciwieństwie do zwykłych elementów elementy dynamiczne nie są dostosowywane i menu Dostosuj na pasku stanu nie są wyświetlane.

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a> CMFCRibbonStatusBar:: AddElement

Dodaje nowy element wstążki do paska stanu wstążki.

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametry

*pElement*<br/>
podczas Wskaźnik do dodanego elementu.

*lpszLabel*<br/>
podczas Etykieta tekstowa elementu.

*bIsVisible*<br/>
podczas PRAWDA, jeśli chcesz dodać element jako widoczny, FAŁSZ, jeśli chcesz dodać element jako ukryty.

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a> CMFCRibbonStatusBar:: addextendedelement

Dodaje element wstążki do rozszerzonego obszaru paska stanu wstążki.

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametry

*pElement*<br/>
podczas Wskaźnik do dodanego elementu.

*lpszLabel*<br/>
podczas Etykieta tekstu elementu.

*bIsVisible*<br/>
podczas PRAWDA, jeśli chcesz dodać element jako widoczny, FAŁSZ, jeśli chcesz dodać element jako ukryty.

### <a name="remarks"></a>Uwagi

Rozszerzony obszar znajduje się po prawej stronie kontrolki pasek stanu.

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a> CMFCRibbonStatusBar:: AddSeparator

Dodaje separator do paska stanu wstążki.

```cpp
void AddSeparator();
```

### <a name="remarks"></a>Uwagi

Struktura dodaje separator po metodzie [CMFCRibbonStatusBar:: AddElement](#addelement). Wstawia ostatni element.

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a> CMFCRibbonStatusBar:: Create

Tworzy pasek stanu wstążki.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
podczas Wskaźnik do okna nadrzędnego.

*dwStyle*<br/>
podczas Logiczne lub kombinacja stylów kontrolek.

*nID*<br/>
podczas Identyfikator kontrolki paska stanu.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli pasek stanu został utworzony pomyślnie, wartość FALSE w przeciwnym razie.

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a> CMFCRibbonStatusBar::CreateEx

Tworzy pasek stanu wstążki o rozszerzonym stylu.

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
Wskaźnik do okna nadrzędnego.

*dwCtrlStyle*<br/>
Logiczne lub kombinacja dodatkowych stylów do tworzenia obiektu paska stanu.

*dwStyle*<br/>
Styl formantu paska stanu.

*nID*<br/>
Identyfikator kontrolki paska stanu.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli pasek stanu został utworzony pomyślnie, wartość FALSE w przeciwnym razie.

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a> CMFCRibbonStatusBar::FindByID

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>Parametry

podczas *uiCmdID*<br/>
podczas Wartość *logiczna*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a> CMFCRibbonStatusBar:: FindElement

Zwraca wskaźnik do elementu, który ma określony identyfikator polecenia.

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>Parametry

*uiID*<br/>
podczas Identyfikator elementu.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do elementu, który ma określony identyfikator polecenia. Wartość NULL, jeśli nie ma takiego elementu.

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a> CMFCRibbonStatusBar:: GetCount

Zwraca liczbę elementów, które znajdują się w głównym obszarze paska stanu wstążki.

```
int GetCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów, które znajdują się w głównym obszarze paska stanu wstążki.

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a> CMFCRibbonStatusBar:: GetElement

Zwraca wskaźnik do elementu, który znajduje się w określonym indeksie.

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
podczas Określa indeks (liczony od zera) elementu, który znajduje się w obszarze głównym kontrolki pasek stanu.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do elementu, który znajduje się w określonym indeksie. Wartość NULL, jeśli indeks jest ujemny lub przekracza liczbę elementów na pasku stanu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a> CMFCRibbonStatusBar::GetExCount

Zwraca liczbę elementów, które znajdują się w rozszerzonym obszarze paska stanu wstążki.

```
int GetExCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów, które znajdują się w rozszerzonym obszarze paska stanu wstążki.

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a> CMFCRibbonStatusBar::GetExElement

Zwraca wskaźnik do elementu, który znajduje się w określonym indeksie w rozszerzonym obszarze paska stanu wstążki. Rozszerzony obszar znajduje się po prawej stronie kontrolki pasek stanu.

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
podczas Określa indeks (liczony od zera) elementu, który znajduje się w rozszerzonym obszarze kontrolki pasek stanu.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do elementu, który znajduje się w określonym indeksie w rozszerzonym obszarze paska stanu wstążki. Wartość NULL, jeśli *nIndex* jest ujemna lub przekracza liczbę elementów w rozszerzonym obszarze paska stanu wstążki.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCRibbonStatusBar::GetExtendedArea

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parametry

podczas *prostokąt*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a> CMFCRibbonStatusBar:: getspace

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
int GetSpace() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a> CMFCRibbonStatusBar::IsBottomFrame

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a> CMFCRibbonStatusBar:: isextendedelement

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>Parametry

podczas *pElement*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a> CMFCRibbonStatusBar:: isinformationmode

Określa, czy tryb informacji jest włączony dla paska stanu wstążki.

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli pasek stanu może być działał w trybie informacji; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

W trybie informacji pasek stanu ukrywa wszystkie zwykłe okienka i wyświetla ciąg komunikatów.

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a> CMFCRibbonStatusBar::OnDrawInformation

Wyświetla ciąg, który pojawia się na pasku stanu wstążki, gdy jest włączony tryb informacji.

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*strInfo*<br/>
podczas Ciąg informacji.

*rectInfo*<br/>
podczas Prostokąt ograniczający.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę w klasie pochodnej, jeśli chcesz dostosować wygląd ciągu informacji na pasku stanu. Użyj metody [CMFCRibbonStatusBar:: SetInformation](#setinformation) , aby umieścić pasek stanu w trybie informacji. W tym trybie pasek stanu ukrywa wszystkie okienka i wyświetla ciąg informacji określony przez *strInfo*.

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a> CMFCRibbonStatusBar::RecalcLayout

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a> CMFCRibbonStatusBar::

Usuwa wszystkie elementy z paska stanu wstążki.

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a> CMFCRibbonStatusBar:: RemoveElement

Usuwa element z określonym IDENTYFIKATORem polecenia z paska stanu wstążki.

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>Parametry

*uiID*<br/>
podczas Identyfikator elementu, który ma zostać usunięty z paska stanu.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli element z określonym *uiID* jest usuwany. W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a> CMFCRibbonStatusBar:: SetInformation

Włącza lub wyłącza tryb informacji dla paska stanu wstążki.

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>Parametry

*lpszInfo*<br/>
podczas Ciąg informacji.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby umieścić pasek stanu w trybie informacji. W tym trybie pasek stanu ukrywa wszystkie okienka i wyświetla ciąg informacji określony przez *lpszInfo*.

Gdy lpszInfo ma wartość NULL, pasek stanu wraca do trybu regularnego.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[Klasa CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
