---
description: 'Dowiedz się więcej na temat: Klasa CFont'
title: Klasa CFont
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 4c3df138c80aeb572a4e449e7fe1065e70b5fe49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184416"
---
# <a name="cfont-class"></a>Klasa CFont

Hermetyzuje czcionkę interfejsu urządzenia graficznego (GDI) systemu Windows i udostępnia funkcje elementów członkowskich do manipulowania czcionką.

## <a name="syntax"></a>Składnia

```
class CFont : public CGdiObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFont:: CFont](#cfont)|Konstruuje `CFont` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFont:: isfont](#createfont)|Inicjuje obiekt `CFont` o określonej charakterystyce.|
|[CFont:: CreateFontIndirect](#createfontindirect)|Inicjuje `CFont` obiekt o cechach określonych w `LOGFONT` strukturze.|
|[CFont:: CreatePointFont](#createpointfont)|Inicjuje `CFont` z określoną wysokością, mierzoną w dziesiątych punktach i kroju pisma.|
|[CFont:: CreatePointFontIndirect](#createpointfontindirect)|Tak samo jak w `CreateFontIndirect` przypadku, gdy wysokość czcionki jest mierzona w dziesiątych punktach, a nie w jednostkach logicznych.|
|[CFont:: FromHandle](#fromhandle)|Zwraca wskaźnik do obiektu, w `CFont` którym znajduje się HFONT systemu Windows.|
|[CFont:: GetLogFont](#getlogfont)|Wypełnia `LOGFONT` Informacje o czcionce logicznej dołączonej do `CFont` obiektu.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFont:: operator HFONT](#operator_hfont)|Zwraca dojście do czcionki interfejsu GDI systemu Windows dołączone do `CFont` obiektu.|

## <a name="remarks"></a>Uwagi

Aby użyć `CFont` obiektu, konstruowania `CFont` obiektu i dołączenia do niego czcionki systemu Windows [](#createfont)przy użyciu funkcji [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont)lub [CreatePointFontIndirect](#createpointfontindirect), a następnie używania jej w celu manipulowania czcionką.

`CreatePointFont`Funkcje i `CreatePointFontIndirect` są często łatwiejsze do użycia niż `CreateFont` lub `CreateFontIndirect` , ponieważ wykonują konwersję wysokości czcionki od rozmiaru punktu do jednostek logicznych automatycznie.

Aby uzyskać więcej informacji na temat `CFont` , zobacz [grafika Objects](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cfontcfont"></a><a name="cfont"></a> CFont:: CFont

Konstruuje `CFont` obiekt.

```
CFont();
```

### <a name="remarks"></a>Uwagi

Obiekt wyników musi być zainicjowany przy użyciu `CreateFont` , `CreateFontIndirect` , `CreatePointFont` lub, `CreatePointFontIndirect` zanim będzie można go użyć.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a> CFont:: isfont

Inicjuje `CFont` obiekt o określonej charakterystyce.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>Parametry

*nHeight*<br/>
Określa żądaną wysokość (w jednostkach logicznych) czcionki. `lfHeight`Aby uzyskać opis, zobacz element członkowski struktury [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)w Windows SDK. Wartość bezwzględna *nHeight* nie może przekraczać 16 384 jednostek urządzeń po przeprowadzeniu konwersji. W przypadku wszystkich porównań, Maper czcionek szuka największej czcionki, która nie przekracza żądanego rozmiaru lub najmniejszej czcionki, jeśli wszystkie czcionki przekroczą żądany rozmiar.

*nWidth*<br/>
Określa średnią szerokość (w jednostkach logicznych) znaków czcionki. Jeśli *nWidth* ma wartość 0, współczynnik proporcji urządzenia zostanie dopasowany do współczynnika proporcji dla dostępnych czcionek, aby znaleźć najbliższy odpowiednik, który jest określany przez wartość bezwzględną różnicy.

*nEscapement*<br/>
Określa kąt (w jednostkach o 0,1 stopni) między wektorem ucieczki i osią x powierzchni wyświetlania. Wektor ucieczki to linia przez początek pierwszego i ostatniego znaku w wierszu. Kąt jest mierzony w lewo od osi x. Aby uzyskać `lfEscapement` więcej informacji, zobacz element członkowski w `LOGFONT` strukturze Windows SDK.

*nOrientation*<br/>
Określa kąt (w jednostkach o 0,1 stopni) między linią bazową znaku a osią x. Kąt jest mierzony w lewo od osi x dla systemów współrzędnych, w których kierunek y jest wyłączony i w prawo od osi x dla systemów współrzędnych, w których kierunek y jest ustawiony.

*nWeight*<br/>
Określa grubość czcionki (w Inked pikselach na 1000). Aby uzyskać więcej informacji, zobacz element członkowski *lfWeight* w `LOGFONT` strukturze Windows SDK. Podane wartości są przybliżone; rzeczywisty wygląd zależy od kroju pisma. Niektóre czcionki mają tylko FW_NORMAL, FW_REGULAR i FW_BOLD wag. Jeśli FW_DONTCARE jest określony, zostanie użyta domyślna waga.

*bItalic*<br/>
Określa, czy czcionka jest kursywą.

*bUnderline*<br/>
Określa, czy czcionka jest podkreślona.

*cStrikeOut*<br/>
Określa, czy znaki w czcionce są wykreślone. Określa czcionkę przekreśloną, jeśli jest ustawiona na wartość różną od zera.

*nCharSet*<br/>
Określa znak czcionki setSee `lfCharSet` element członkowski w `LOGFONT` strukturze Windows SDK dla listy wartości.

Zestaw znaków OEM jest zależny od systemu.

Czcionki z innymi zestawami znaków mogą istnieć w systemie. Aplikacja, która używa czcionki z nieznanego zestawu znaków, nie może próbować tłumaczyć ani interpretować ciągów, które mają być renderowane z tą czcionką. Zamiast tego ciągi powinny być przekazywane bezpośrednio do sterownika urządzenia wyjściowego.

Funkcja mapowania czcionek nie używa wartości DEFAULT_CHARSET. Aplikacja może używać tej wartości, aby zezwalać na pełne opisywanie czcionki logicznej przez nazwę i rozmiar czcionki. Jeśli czcionka o podanej nazwie nie istnieje, czcionka z dowolnego zestawu znaków może zostać zastąpiona dla określonej czcionki. Aby uniknąć nieoczekiwanych wyników, aplikacje powinny używać wartości DEFAULT_CHARSET oszczędnie.

*nOutPrecision*<br/>
Określa żądaną precyzję wyjściową. Precyzja wyjściowa określa, jak blisko dane wyjściowe muszą być zgodne z wymaganą wysokością czcionki, szerokością, orientacją znaków, ucieczką i szerokością. Zobacz `lfOutPrecision` element członkowski w `LOGFONT` strukturze Windows SDK, aby uzyskać listę wartości i uzyskać więcej informacji.

*nClipPrecision*<br/>
Określa żądaną precyzję przycinania. Precyzja przycinania definiuje sposób obcinania znaków, które są częściowo poza regionem przycinania. Zobacz `lfClipPrecision` element członkowski w `LOGFONT` strukturze w Windows SDK, aby uzyskać listę wartości.

Aby można było użyć osadzonej czcionki tylko do odczytu, aplikacja musi określić CLIP_ENCAPSULATE.

Aby osiągnąć spójną rotację czcionek urządzenia, TrueType i Vector, aplikacja może użyć operatora OR do łączenia wartości CLIP_LH_ANGLES z dowolną inną wartością *nClipPrecision* . Jeśli ustawiono bit CLIP_LH_ANGLES, obroty dla wszystkich czcionek są zależne od tego, czy orientacja układu współrzędnych jest pozostawiona, czy w prawo. (Aby uzyskać więcej informacji na temat orientacji systemów współrzędnych, zobacz opis parametru *nOrientation* ). Jeśli CLIP_LH_ANGLES nie jest ustawiona, czcionki urządzenia zawsze są obracane w lewo, ale obrót innych czcionek zależy od orientacji układu współrzędnych.

*nQuality*<br/>
Określa jakość wyjściową czcionki, która określa, jak starannie interfejs GDI musi próbować dopasować atrybuty czcionki logicznej do tych z rzeczywistej czcionki fizycznej. Zobacz `lfQuality` element członkowski w `LOGFONT` strukturze w Windows SDK, aby uzyskać listę wartości.

*nPitchAndFamily*<br/>
Określa gęstość i rodzinę czcionki. Zobacz `lfPitchAndFamily` element członkowski w `LOGFONT` strukturze Windows SDK, aby uzyskać listę wartości i uzyskać więcej informacji.

*lpszFacename*<br/>
`CString`Wskaźnik lub do ciągu zakończonego wartością null, który określa nazwę kroju czcionki. Długość tego ciągu nie może przekraczać 30 znaków. Funkcja [EnumFontFamilies](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) systemu Windows może służyć do wyliczania wszystkich aktualnie dostępnych czcionek. Jeśli *lpszFacename* ma wartość null, w interfejsie GDI używany jest krój niezależny od urządzenia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Czcionkę można następnie wybrać jako czcionkę dla dowolnego kontekstu urządzenia.

`CreateFont`Funkcja nie tworzy nowej czcionki interfejsu GDI systemu Windows. Po prostu wybiera najbliższe dopasowanie z czcionek fizycznych dostępnych dla GDI.

Aplikacje mogą używać ustawień domyślnych dla większości parametrów podczas tworzenia czcionki logicznej. Parametry, które powinny mieć zawsze określone wartości, to *nHeight* i *lpszFacename*. Jeśli *nHeight* i *lpszFacename* nie są ustawiane przez aplikację, tworzona czcionka logiczna jest zależna od urządzenia.

Po zakończeniu pracy z `CFont` obiektem utworzonym przez `CreateFont` funkcję Użyj, `CDC::SelectObject` Aby wybrać inną czcionkę w kontekście urządzenia, a następnie usuń `CFont` obiekt, który nie jest już wymagany.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a> CFont:: CreateFontIndirect

Inicjuje `CFont` obiekt o cechach określonych w strukturze [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw).

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Parametry

*lpLogFont*<br/>
Wskazuje `LOGFONT` strukturę, która definiuje charakterystykę czcionki logicznej.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Czcionkę można następnie wybrać jako bieżącą czcionkę dla każdego urządzenia.

Ta czcionka ma cechy określone w strukturze [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) . W przypadku wybrania czcionki przy użyciu funkcji "elementu członkowskiego" [przechwytywania:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) , funkcja mapowania czcionek GDI próbuje dopasować czcionkę logiczną do istniejącej czcionki fizycznej. Jeśli funkcja mapowania czcionek nie może znaleźć dokładnego dopasowania dla czcionki logicznej, zapewnia alternatywną czcionkę, której cechy są zgodne z wieloma żądanymi właściwościami, jak to możliwe.

Gdy nie potrzebujesz już `CFont` obiektu utworzonego przez `CreateFontIndirect` funkcję, użyj, `CDC::SelectObject` Aby wybrać inną czcionkę w kontekście urządzenia, a następnie usuń `CFont` obiekt, który nie jest już potrzebny.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a> CFont:: CreatePointFont

Ta funkcja zapewnia prosty sposób tworzenia czcionki o określonym kroju i rozmiarze punktu.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametry

*nPointSize*<br/>
Żądana wysokość czcionki w dziesiątych punktach. (Na przykład Przekaż 120, aby zażądać czcionki 12-punktowej).

*lpszFaceName*<br/>
`CString`Wskaźnik lub do ciągu zakończonego wartością null, który określa nazwę kroju czcionki. Długość tego ciągu nie może przekraczać 30 znaków. Funkcja EnumFontFamilies systemu Windows może służyć do wyliczania wszystkich aktualnie dostępnych czcionek. Jeśli *lpszFaceName* ma wartość null, w interfejsie GDI używany jest krój niezależny od urządzenia.

*Domeny*<br/>
Wskaźnik do obiektu [przechwytywania](../../mfc/reference/cdc-class.md) , który ma zostać użyty do przekonwertowania wysokości w *nPointSize* na jednostki logiczne. Jeśli wartość jest równa NULL, do konwersji jest używany kontekst urządzenia ekranu.

### <a name="return-value"></a>Wartość zwracana

Wartość różna od zera, jeśli się powiedzie, w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Automatycznie konwertuje wysokość w *nPointSize* na jednostki logiczne przy użyciu obiektu przerzutowania wskazywanego przez *PDC*.

Po zakończeniu pracy z `CFont` obiektem utworzonym przez `CreatePointFont` funkcję, najpierw wybierz czcionkę z kontekstu urządzenia, a następnie usuń `CFont` obiekt.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a> CFont:: CreatePointFontIndirect

Ta funkcja jest taka sama jak [CreateFontIndirect](#createfontindirect) , z tą różnicą, że `lfHeight` element członkowski `LOGFONT` jest interpretowany w dziesiątych punktach, a nie w jednostkach urządzeń.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametry

*lpLogFont*<br/>
Wskazuje strukturę [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) , która definiuje charakterystykę czcionki logicznej. `lfHeight`Składowa `LOGFONT` struktury jest mierzona w dziesiątych punktach, a nie w jednostkach logicznych. (Na przykład ustaw wartość `lfHeight` 120, aby zażądać czcionki 12-punktowej).

*Domeny*<br/>
Wskaźnik do obiektu [przechwytywania](../../mfc/reference/cdc-class.md) , który ma zostać użyty do przekonwertowania wysokości w `lfHeight` jednostkach logicznych. Jeśli wartość jest równa NULL, do konwersji jest używany kontekst urządzenia ekranu.

### <a name="return-value"></a>Wartość zwracana

Wartość różna od zera, jeśli się powiedzie, w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja automatycznie konwertuje wysokość w `lfHeight` jednostkach logicznych przy użyciu obiektu przerzutowania wskazywanego przez *PDC* przed przekazaniem `LOGFONT` struktury do systemu Windows.

Po zakończeniu pracy z `CFont` obiektem utworzonym przez `CreatePointFontIndirect` funkcję, najpierw wybierz czcionkę z kontekstu urządzenia, a następnie usuń `CFont` obiekt.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a> CFont:: FromHandle

Zwraca wskaźnik do obiektu, `CFont` gdy nadaje dojść HFONT do obiektu czcionki GDI systemu Windows.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Parametry

*hFont*<br/>
Dojście HFONT do czcionki systemu Windows.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CFont` obiektu, jeśli się powiedzie; w przeciwnym razie wartość null.

### <a name="remarks"></a>Uwagi

Jeśli `CFont` obiekt nie jest jeszcze dołączony do dojścia, `CFont` tworzony jest obiekt tymczasowy i jest on dołączony. Ten `CFont` obiekt tymczasowy jest prawidłowy tylko do następnego czasu, gdy aplikacja ma czas bezczynności w pętli zdarzeń, podczas gdy wszystkie tymczasowe obiekty graficzne są usuwane. Innym sposobem wymawiania tego jest to, że obiekt tymczasowy jest prawidłowy tylko podczas przetwarzania jednego komunikatu w oknie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a> CFont:: GetLogFont

Wywołaj tę funkcję, aby pobrać kopię `LOGFONT` struktury dla programu `CFont` .

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Parametry

*pLogFont*<br/>
Wskaźnik do struktury [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) , aby otrzymać informacje o czcionce.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli funkcja się powiedzie, w przeciwnym razie 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a> CFont:: operator HFONT

Użyj tego operatora, aby uzyskać uchwyt interfejsu GDI systemu Windows dla czcionki dołączonej do `CFont` obiektu.

```
operator HFONT() const;
```

### <a name="return-value"></a>Wartość zwracana

Uchwyt obiektu czcionki GDI systemu Windows, do którego dołączono `CFont` ; w przeciwnym razie wartość null.

### <a name="remarks"></a>Uwagi

Ponieważ ten operator jest automatycznie używany do konwersji z `CFont` do [czcionek i tekstu](/windows/win32/gdi/fonts-and-text), można przekazać `CFont` obiekty do funkcji, które oczekują HFONTs.

Aby uzyskać więcej informacji na temat używania obiektów graficznych, zobacz temat [obiekty graficzne](/windows/win32/gdi/graphic-objects) w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>Zobacz także

[Przykład HIERSVR MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
