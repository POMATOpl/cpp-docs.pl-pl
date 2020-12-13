---
description: 'Dowiedz się więcej na temat: Klasa CMFCPreviewCtrlImpl'
title: Klasa CMFCPreviewCtrlImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: 09e4b8e023a55110986aafccfd2646d8e7775c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334732"
---
# <a name="cmfcpreviewctrlimpl-class"></a>Klasa CMFCPreviewCtrlImpl

Ta klasa implementuje okno umieszczane w oknie hosta dostarczonym przez powłokę do rozbudowanej wersji zapoznawczej.

## <a name="syntax"></a>Składnia

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Destruktory obiektu kontroli wersji zapoznawczej.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Konstruuje obiekt kontrolki podglądu.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPreviewCtrlImpl:: Create](#create)|Przeciążone. Wywoływane przez zaawansowaną procedurę obsługi podglądu do utworzenia okna systemu Windows.|
|[CMFCPreviewCtrlImpl::D Estroy](#destroy)|Wywoływane przez zaawansowaną procedurę obsługi podglądu, gdy trzeba zniszczyć tę kontrolkę.|
|[CMFCPreviewCtrlImpl:: Focus](#focus)|Ustawia fokus wprowadzania dla tego formantu.|
|[CMFCPreviewCtrlImpl:: GetDocument](#getdocument)|Zwraca dokument połączony z tą kontrolką podglądu.|
|[CMFCPreviewCtrlImpl:: redraw](#redraw)|Informuje tę kontrolkę o ponownym narysowaniu.|
|[CMFCPreviewCtrlImpl:: SetDocument](#setdocument)|Wywoływane przez procedurę obsługi podglądu, aby utworzyć relację między implementacją dokumentu a kontrolką w wersji zapoznawczej.|
|[CMFCPreviewCtrlImpl:: SetHost](#sethost)|Ustawia nowy element nadrzędny dla tej kontrolki.|
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Wywoływana przez zaawansowaną procedurę obsługi podglądu, gdy musi ona ustawiać wizualizacje zawartości bogatej wersji zapoznawczej.|
|[CMFCPreviewCtrlImpl:: SetRect](#setrect)|Ustawia nowy prostokąt ograniczający dla tej kontrolki.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::D oPaint](#dopaint)|Wywoływane przez platformę w celu renderowania wersji zapoznawczej.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPreviewCtrlImpl:: m_clrBackColor](#m_clrbackcolor)|Kolor tła okna podglądu.|
|[CMFCPreviewCtrlImpl:: m_clrTextColor](#m_clrtextcolor)|Kolor tekstu okna podglądu.|
|[CMFCPreviewCtrlImpl:: m_font](#m_font)|Czcionka używana do wyświetlania tekstu w oknie podglądu.|
|[CMFCPreviewCtrlImpl:: m_pDocument](#m_pdocument)|Wskaźnik do dokumentu, którego zawartość jest wyświetlana w formancie.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Konstruuje obiekt kontrolki podglądu.

### <a name="syntax"></a>Składnia

CMFCPreviewCtrlImpl();

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a> CMFCPreviewCtrlImpl:: Create

Przeciążone. Wywoływane przez zaawansowaną procedurę obsługi podglądu do utworzenia okna systemu Windows.

### <a name="syntax"></a>Składnia

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>Parametry

*hWndParent*<br/>
Dojście do okna hosta dostarczone przez powłokę do rozbudowanej wersji zapoznawczej.

*Republika*<br/>
Określa początkowy rozmiar i położenie okna.

*pContext*<br/>
Wskaźnik do kontekstu tworzenia.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli tworzenie powiodło się; w przeciwnym razie FALSE.

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a> CMFCPreviewCtrlImpl::D Estroy

Wywoływane przez zaawansowaną procedurę obsługi podglądu, gdy trzeba zniszczyć tę kontrolkę.

### <a name="syntax"></a>Składnia

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a> CMFCPreviewCtrlImpl::D oPaint

Wywoływane przez platformę w celu renderowania wersji zapoznawczej.

### <a name="syntax"></a>Składnia

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Wskaźnik do kontekstu urządzenia do malowania.

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a> CMFCPreviewCtrlImpl:: Focus

Ustawia fokus wprowadzania dla tego formantu.

### <a name="syntax"></a>Składnia

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a> CMFCPreviewCtrlImpl:: GetDocument

Zwraca dokument połączony z tą kontrolką podglądu.

### <a name="syntax"></a>Składnia

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do dokumentu, którego zawartość jest wyświetlana w formancie.

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl:: m_clrBackColor

Kolor tła okna podglądu.

### <a name="syntax"></a>Składnia

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl:: m_clrTextColor

Kolor tekstu okna podglądu.

### <a name="syntax"></a>Składnia

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a> CMFCPreviewCtrlImpl:: m_font czcionka używana do wyświetlania tekstu w oknie podglądu.

### <a name="syntax"></a>Składnia

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a> CMFCPreviewCtrlImpl:: m_pDocument

Wskaźnik do dokumentu, którego zawartość jest wyświetlana w formancie.

### <a name="syntax"></a>Składnia

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a> CMFCPreviewCtrlImpl:: redraw

Informuje tę kontrolkę o ponownym narysowaniu.

### <a name="syntax"></a>Składnia

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a> CMFCPreviewCtrlImpl:: SetDocument

Wywoływane przez procedurę obsługi podglądu, aby utworzyć relację między implementacją dokumentu a kontrolką w wersji zapoznawczej.

### <a name="syntax"></a>Składnia

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Parametry

*pDocument*<br/>
Wskaźnik do implementacji dokumentu.

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a> CMFCPreviewCtrlImpl:: SetHost

Ustawia nowy element nadrzędny dla tej kontrolki.

### <a name="syntax"></a>Składnia

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Parametry

*hWndParent*<br/>
Uchwyt do nowego okna nadrzędnego.

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals

Wywoływana przez zaawansowaną procedurę obsługi podglądu, gdy musi ona ustawiać wizualizacje zawartości bogatej wersji zapoznawczej.

### <a name="syntax"></a>Składnia

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Parametry

*clrBack*<br/>
Kolor tła okna podglądu.

*clrText*<br/>
Kolor tekstu okna podglądu.

*plf*<br/>
Czcionka używana do wyświetlania tekstu w oknie podglądu.

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a> CMFCPreviewCtrlImpl:: SetRect

Ustawia nowy prostokąt ograniczający dla tej kontrolki.

### <a name="syntax"></a>Składnia

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Parametry

*Republika*<br/>
Określa nowy rozmiar i położenie kontrolki podglądu.

*bRedraw*<br/>
Określa, czy kontrolka ma być odświeżana.

### <a name="remarks"></a>Uwagi

Zwykle nowy prostokąt ograniczający jest ustawiany, gdy zmieniany jest rozmiar kontrolki hosta.

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a> CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl

Destruktory obiektu kontroli wersji zapoznawczej.

### <a name="syntax"></a>Składnia

```
virtual ~CMFCPreviewCtrlImpl();
```
