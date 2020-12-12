---
description: 'Dowiedz się więcej na temat: Klasa CFontHolder'
title: Klasa CFontHolder
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 1670bd9a00c5b6f7990c15ba31d7256afb8d4031
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184299"
---
# <a name="cfontholder-class"></a>Klasa CFontHolder

Implementuje właściwość "podstawowe czcionki" i hermetyzuje funkcjonalność obiektu czcionki systemu Windows i `IFont` interfejsu.

## <a name="syntax"></a>Składnia

```
class CFontHolder
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|Konstruuje `CFontHolder` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Pobiera ciąg wyświetlany w przeglądarce właściwości kontenera.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Zwraca `IDispatch` interfejs czcionki.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Zwraca dojście do czcionki systemu Windows.|
|[CFontHolder::InitializeFont](#initializefont)|Inicjuje `CFontHolder` obiekt.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|Pobiera informacje dotyczące powiązanej czcionki.|
|[CFontHolder::ReleaseFont](#releasefont)|Rozłącza `CFontHolder` obiekt od `IFont` `IFontNotification` interfejsów i.|
|[CFontHolder:: SELECT](#select)|Wybiera zasób czcionki w kontekście urządzenia.|
|[CFontHolder:: SetFont](#setfont)|Łączy `CFontHolder` obiekt z `IFont` interfejsem.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CFontHolder:: m_pFont](#m_pfont)|Wskaźnik do `CFontHolder` `IFont` interfejsu obiektu.|

## <a name="remarks"></a>Uwagi

`CFontHolder` nie ma klasy bazowej.

Użyj tej klasy, aby zaimplementować niestandardowe właściwości czcionki dla kontrolki. Aby uzyskać informacje na temat tworzenia takich właściwości, zobacz artykuł [formanty ActiveX: Używanie czcionek](../../mfc/mfc-activex-controls-using-fonts.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CFontHolder`

## <a name="requirements"></a>Wymagania

**Nagłówek:** 'afxctl. h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a> CFontHolder::CFontHolder

Konstruuje `CFontHolder` obiekt.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Parametry

*pNotify*<br/>
Wskaźnik do `IPropertyNotifySink` interfejsu czcionki.

### <a name="remarks"></a>Uwagi

Musisz wywołać, `InitializeFont` Aby zainicjować obiekt otrzymany przed użyciem.

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a> CFontHolder::GetDisplayString

Pobiera ciąg, który może być wyświetlany w przeglądarce właściwości kontenera.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametry

*strValue*<br/>
Odwołanie do [CString](../../atl-mfc-shared/reference/cstringt-class.md) , która ma przechowywać ciąg wyświetlania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli ciąg został pomyślnie pobrany; w przeciwnym razie 0.

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a> CFontHolder::GetFontDispatch

Wywołaj tę funkcję, aby pobrać wskaźnik do interfejsu wysyłania czcionki.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CFontHolder` `IFontDisp` interfejsu obiektu. Należy zauważyć, że funkcja wywołująca `GetFontDispatch` musi wywołać `IUnknown::Release` ten wskaźnik interfejsu po zakończeniu z nim.

### <a name="remarks"></a>Uwagi

Wywołaj `InitializeFont` przed wywołaniem metody `GetFontDispatch` .

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a> CFontHolder::GetFontHandle

Wywołaj tę funkcję, aby uzyskać uchwyt do czcionki systemu Windows.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametry

*cyLogical*<br/>
Wysokość (w jednostkach logicznych) prostokąta, w którym jest rysowany formant.

*cyHimetric*<br/>
Wysokość formantu w jednostkach MM_HIMETRIC.

### <a name="return-value"></a>Wartość zwracana

Uchwyt do obiektu Font; w przeciwnym razie wartość NULL.

### <a name="remarks"></a>Uwagi

Stosunek *cyLogical* i *cyHimetric* jest używany do obliczania odpowiedniego rozmiaru wyświetlania w jednostkach logicznych dla rozmiaru punktu czcionki wyrażonego w jednostkach MM_HIMETRIC:

Display size = ( *cyLogical*  /  *cyHimetric*) X rozmiar czcionki

Wersja bez parametrów zwraca dojście do rozmiaru czcionki poprawnie dla ekranu.

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a> CFontHolder::InitializeFont

Inicjuje `CFontHolder` obiekt.

```cpp
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametry

*pFontDesc*<br/>
Wskaźnik do struktury opisu czcionki ( [FONTDESC](/windows/win32/api/olectl/ns-olectl-fontdesc)), która określa charakterystykę czcionki.

*pFontDispAmbient*<br/>
Wskaźnik na właściwość Font otaczający kontenera.

### <a name="remarks"></a>Uwagi

Jeśli *pFontDispAmbient* nie ma wartości null, `CFontHolder` obiekt jest połączony z klonem `IFont` interfejsu używanego przez właściwość otaczającej czcionki kontenera.

Jeśli *pFontDispAmbient* ma wartość null, zostanie utworzony nowy obiekt Font z opisu czcionki wskazywanym przez *pFontDesc* lub, jeśli *pFontDesc* ma wartość null, z domyślnego opisu.

Wywołaj tę funkcję po utworzeniu `CFontHolder` obiektu.

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a> CFontHolder:: m_pFont

Wskaźnik do `CFontHolder` `IFont` interfejsu obiektu.

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a> CFontHolder::QueryTextMetrics

Pobiera informacje o czcionce fizycznej reprezentowanej przez `CFontHolder` obiekt.

```cpp
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Parametry

*lptm*<br/>
Wskaźnik do struktury [TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw) , która będzie odbierać informacje.

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a> CFontHolder::ReleaseFont

Ta funkcja rozłącza `CFontHolder` obiekt od jego `IFont` interfejsu.

```cpp
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a> CFontHolder:: SELECT

Wywołaj tę funkcję, aby wybrać czcionkę kontrolki w określonym kontekście urządzenia.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Kontekst urządzenia, do którego wybrana jest czcionka.

*cyLogical*<br/>
Wysokość (w jednostkach logicznych) prostokąta, w którym jest rysowany formant.

*cyHimetric*<br/>
Wysokość formantu w jednostkach MM_HIMETRIC.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do czcionki, która jest zastępowana.

### <a name="remarks"></a>Uwagi

Zobacz [GetFontHandle](#getfonthandle) , aby zapoznać się z omówieniem parametrów *cyLogical* i *cyHimetric* .

## <a name="cfontholdersetfont"></a><a name="setfont"></a> CFontHolder:: SetFont

Zwalnia istniejącą czcionkę i łączy `CFontHolder` obiekt z `IFont` interfejsem.

```cpp
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Parametry

*pNewFont*<br/>
Wskaźnik do nowego `IFont` interfejsu.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CPropExchange](../../mfc/reference/cpropexchange-class.md)
