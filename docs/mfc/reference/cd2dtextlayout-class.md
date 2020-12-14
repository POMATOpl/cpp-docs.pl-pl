---
description: 'Dowiedz się więcej na temat: Klasa CD2DTextLayout'
title: Klasa CD2DTextLayout
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: 164c8ed5561be6e8f9ee59b07d0aecaced5f7c81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240549"
---
# <a name="cd2dtextlayout-class"></a>Klasa CD2DTextLayout

Otoka dla IDWriteTextLayout.

## <a name="syntax"></a>Składnia

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Konstruuje obiekt CD2DTextLayout.|
|[CD2DTextLayout:: ~ CD2DTextLayout](#_dtorcd2dtextlayout)|Destruktor. Wywołuje się, gdy obiekt układu tekstu D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextLayout:: Create](#create)|Tworzy element CD2DTextLayout. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::D Estroy](#destroy)|Niszczy obiekt CD2DTextLayout. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout:: Get](#get)|Zwraca interfejs IDWriteTextLayout|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Kopiuje nazwę rodziny czcionek tekstu na określonej pozycji.|
|[CD2DTextLayout:: getlocalname](#getlocalename)|Pobiera nazwę ustawień regionalnych dla tekstu w określonej pozycji.|
|[CD2DTextLayout:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|
|[CD2DTextLayout:: Recreate](#recreate)|Tworzy ponowną CD2DTextLayout. (Zastępuje [CD2DResource:: Recreate](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Ustawia nazwę rodziny czcionek zakończonych znakiem null dla tekstu w określonym zakresie tekstu|
|[CD2DTextLayout:: setLocalName](#setlocalename)|Ustawia nazwę ustawień regionalnych dla tekstu w określonym zakresie tekstu|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextLayout:: operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|Zwraca interfejs IDWriteTextLayout|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextLayout:: m_pTextLayout](#m_ptextlayout)|Wskaźnik do elementu IDWriteTextLayout.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a> CD2DTextLayout:: ~ CD2DTextLayout

Destruktor. Wywołuje się, gdy obiekt układu tekstu D2D jest niszczony.

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a> CD2DTextLayout::CD2DTextLayout

Konstruuje obiekt CD2DTextLayout.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*strText*<br/>
Obiekt CString, który zawiera ciąg służący do tworzenia nowego obiektu CD2DTextLayout.

*textFormat*<br/>
Obiekt CString, który zawiera format do zastosowania do ciągu.

*sizeMax*<br/>
Rozmiar pola układu.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a> CD2DTextLayout:: Create

Tworzy element CD2DTextLayout.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a> CD2DTextLayout::D Estroy

Niszczy obiekt CD2DTextLayout.

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a> CD2DTextLayout:: Get

Zwraca interfejs IDWriteTextLayout

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu IDWriteTextLayout lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextLayout::GetFontFamilyName

Kopiuje nazwę rodziny czcionek tekstu na określonej pozycji.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametry

*currentPosition*<br/>
Pozycja tekstu do sprawdzenia.

*textRange*<br/>
Zakres tekstu, który ma takie samo formatowanie jak tekst w pozycji określonej przez currentPosition. Oznacza to, że przebieg ma dokładne formatowanie jako określone położenie, w tym między innymi nazwę rodziny czcionek.

### <a name="return-value"></a>Wartość zwracana

Obiekt CString, który zawiera bieżącą nazwę rodziny czcionek.

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a> CD2DTextLayout:: getlocalname

Pobiera nazwę ustawień regionalnych dla tekstu w określonej pozycji.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametry

*currentPosition*<br/>
Pozycja tekstu do sprawdzenia.

*textRange*<br/>
Zakres tekstu, który ma takie samo formatowanie jak tekst w pozycji określonej przez currentPosition. Oznacza to, że przebieg ma dokładne formatowanie jako określone położenie, w tym, ale nie ograniczone do nazwy ustawień regionalnych.

### <a name="return-value"></a>Wartość zwracana

Obiekt CString, który zawiera bieżącą nazwę ustawień regionalnych.

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a> CD2DTextLayout:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a> CD2DTextLayout:: m_pTextLayout

Wskaźnik do elementu IDWriteTextLayout.

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a> CD2DTextLayout:: operator IDWriteTextLayout *

Zwraca interfejs IDWriteTextLayout

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu IDWriteTextLayout lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a> CD2DTextLayout:: Recreate

Tworzy ponowną CD2DTextLayout.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a> CD2DTextLayout::SetFontFamilyName

Ustawia nazwę rodziny czcionek zakończonych znakiem null dla tekstu w określonym zakresie tekstu

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametry

*pwzFontFamilyName*<br/>
Nazwa rodziny czcionek stosowana do całego ciągu tekstowego w zakresie określonym przez element TextRange

*textRange*<br/>
Zakres tekstu, do którego odnosi się ta zmiana

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a> CD2DTextLayout:: setLocalName

Ustawia nazwę ustawień regionalnych dla tekstu w określonym zakresie tekstu

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametry

*pwzLocaleName*<br/>
Ciąg nazw ustawień regionalnych zakończonych wartością null

*textRange*<br/>
Zakres tekstu, do którego odnosi się ta zmiana

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
