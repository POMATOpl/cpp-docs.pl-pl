---
description: 'Dowiedz się więcej na temat: Klasa CD2DTextFormat'
title: Klasa CD2DTextFormat
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: fc87aec6acb0e1eae0211555f1bdc943079081f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338332"
---
# <a name="cd2dtextformat-class"></a>Klasa CD2DTextFormat

Otoka dla IDWriteTextFormat.

## <a name="syntax"></a>Składnia

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Konstruuje obiekt CD2DTextFormat.|
|[CD2DTextFormat:: ~ CD2DTextFormat](#_dtorcd2dtextformat)|Destruktor. Wywołuje się, gdy obiekt formatu tekstu D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextFormat:: Create](#create)|Tworzy element CD2DTextFormat. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::D Estroy](#destroy)|Niszczy obiekt CD2DTextFormat. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat:: Get](#get)|Zwraca interfejs IDWriteTextFormat|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Pobiera kopię nazwy rodziny czcionek.|
|[CD2DTextFormat:: getlocalname](#getlocalename)|Pobiera kopię nazwy ustawień regionalnych.|
|[CD2DTextFormat:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|
|[CD2DTextFormat:: Recreate](#recreate)|Tworzy ponowną CD2DTextFormat. (Zastępuje [CD2DResource:: Recreate](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextFormat:: operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Zwraca interfejs IDWriteTextFormat|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DTextFormat:: m_pTextFormat](#m_ptextformat)|Wskaźnik do elementu IDWriteTextFormat.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a> CD2DTextFormat:: ~ CD2DTextFormat

Destruktor. Wywołuje się, gdy obiekt formatu tekstu D2D jest niszczony.

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a> CD2DTextFormat::CD2DTextFormat

Konstruuje obiekt CD2DTextFormat.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*strFontFamilyName*<br/>
Obiekt CString, który zawiera nazwę rodziny czcionek.

*fontSize*<br/>
Rozmiar logiczny czcionki w jednostkach DIP ("piksel niezależny od urządzenia"). DIPequals 1/96 cala.

*fontWeight*<br/>
Wartość, która wskazuje grubość czcionki dla obiektu tekstowego.

*fontStyle*<br/>
Wartość, która wskazuje styl czcionki dla obiektu tekstu.

*fontStretch*<br/>
Wartość, która wskazuje na rozciągnięcie czcionki dla obiektu tekstowego.

*strFontLocale*<br/>
Obiekt CString, który zawiera nazwę ustawień regionalnych.

*pFontCollection*<br/>
Wskaźnik do obiektu kolekcji czcionek. Gdy jest to wartość NULL, wskazuje systemową kolekcję czcionek.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dtextformatcreate"></a><a name="create"></a> CD2DTextFormat:: Create

Tworzy element CD2DTextFormat.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a> CD2DTextFormat::D Estroy

Niszczy obiekt CD2DTextFormat.

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a> CD2DTextFormat:: Get

Zwraca interfejs IDWriteTextFormat

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu IDWriteTextFormat lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextFormat::GetFontFamilyName

Pobiera kopię nazwy rodziny czcionek.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Wartość zwracana

Obiekt CString, który zawiera bieżącą nazwę rodziny czcionek.

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a> CD2DTextFormat:: getlocalname

Pobiera kopię nazwy ustawień regionalnych.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Wartość zwracana

Obiekt CString, który zawiera bieżącą nazwę ustawień regionalnych.

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a> CD2DTextFormat:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a> CD2DTextFormat:: m_pTextFormat

Wskaźnik do elementu IDWriteTextFormat.

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a> CD2DTextFormat:: operator IDWriteTextFormat *

Zwraca interfejs IDWriteTextFormat

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu IDWriteTextFormat lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a> CD2DTextFormat:: Recreate

Tworzy ponowną CD2DTextFormat.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
