---
description: 'Dowiedz się więcej na temat: Klasa CRectTracker'
title: Klasa CRectTracker
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 8406b6b45a99ca2e1816cb650f243fcea2db8ddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343023"
---
# <a name="crecttracker-class"></a>Klasa CRectTracker

Umożliwia wyświetlanie, przenoszenie i zmianę rozmiaru elementu w różny sposób.

## <a name="syntax"></a>Składnia

```
class CRectTracker
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRectTracker:: CRectTracker](#crecttracker)|Konstruuje `CRectTracker` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRectTracker:: AdjustRect](#adjustrect)|Wywoływana, gdy zmieniany jest rozmiar prostokąta.|
|[CRectTracker::D RAW](#draw)|Renderuje prostokąt.|
|[CRectTracker::D rawTrackerRect](#drawtrackerrect)|Wywołuje się, gdy rysuje obramowanie `CRectTracker` obiektu.|
|[CRectTracker:: GetHandleMask](#gethandlemask)|Wywołuje się, by uzyskać maskę `CRectTracker` uchwytów zmiany rozmiaru elementu.|
|[CRectTracker:: GetTrueRect](#gettruerect)|Zwraca szerokość i wysokość prostokąta, w tym uchwyty zmiany rozmiaru.|
|[CRectTracker:: HitTest](#hittest)|Zwraca bieżącą pozycję kursora powiązanego z `CRectTracker` obiektem.|
|[CRectTracker:: NormalizeHit](#normalizehit)|Normalizuje kod testu trafień.|
|[CRectTracker:: OnChangedRect](#onchangedrect)|Wywoływana, gdy Zmieniono rozmiar lub przeniesienie prostokąta.|
|[CRectTracker:: SetCursor](#setcursor)|Ustawia kursor, w zależności od jego położenia nad prostokątem.|
|[CRectTracker:: Track](#track)|Zezwala użytkownikowi na manipulowanie prostokątem.|
|[CRectTracker:: TrackRubberBand](#trackrubberband)|Zezwala użytkownikowi na "gumowe" zaznaczenie.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CRectTracker:: m_nHandleSize](#m_nhandlesize)|Określa rozmiar uchwytów zmiany rozmiaru.|
|[CRectTracker:: m_nStyle](#m_nstyle)|Bieżące style śledzenia.|
|[CRectTracker:: m_rect](#m_rect)|Bieżąca pozycja (w pikselach) prostokąta.|
|[CRectTracker:: m_sizeMin](#m_sizemin)|Określa minimalną szerokość i wysokość prostokąta.|

## <a name="remarks"></a>Uwagi

`CRectTracker` nie ma klasy bazowej.

Chociaż `CRectTracker` Klasa została zaprojektowana tak, aby umożliwić użytkownikowi współdziałanie z elementami OLE przy użyciu interfejsu graficznego, jego użycie nie jest ograniczone do aplikacji obsługujących technologię OLE. Można go użyć wszędzie tam, gdzie jest wymagany interfejs użytkownika.

`CRectTracker` Obramowanie może być liniami pełnymi lub kropkowanymi. Element może mieć zakreskowane obramowanie lub nałożone przy użyciu wzorca kreskowanego, aby wskazać różne stany elementu. Można umieścić osiem uchwytów zmiany rozmiaru na zewnątrz lub wewnątrz obramowania elementu. (Aby uzyskać wyjaśnienie uchwytów zmiany rozmiaru, zobacz [GetHandleMask](#gethandlemask)). Na koniec, a `CRectTracker` pozwala zmienić orientację elementu w trakcie zmiany rozmiarów.

Do użycia `CRectTracker` , konstruowania `CRectTracker` obiektu i określania, które Stany wyświetlania są inicjowane. Następnie można użyć tego interfejsu, aby dać użytkownikowi informacje zwrotne o bieżącym stanie elementu OLE skojarzonego z `CRectTracker` obiektem.

Aby uzyskać więcej informacji na temat korzystania z programu `CRectTracker` , zobacz informacje o [śledzeniu](../../mfc/trackers.md)artykułu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CRectTracker`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxext. h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a> CRectTracker:: AdjustRect

Wywoływane przez platformę, gdy zmieniany jest rozmiar prostokąta śledzenia przy użyciu uchwytu zmiany rozmiaru.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Parametry

*nHandle*<br/>
Używany indeks dojścia.

*lpRect*<br/>
Wskaźnik do bieżącego rozmiaru prostokąta. (Rozmiar prostokąta jest określony na podstawie jego wysokości i szerokości).

### <a name="remarks"></a>Uwagi

Domyślne zachowanie tej funkcji umożliwia zmianę orientacji prostokąta tylko wtedy `Track` , gdy `TrackRubberBand` są wywoływane z odwracaniem.

Zastąp tę funkcję, aby kontrolować dopasowanie prostokąta śledzenia podczas operacji przeciągania. Jedną z metod jest dostosowanie współrzędnych określonych przez *lpRect* przed zwróceniem.

Specjalne funkcje, które nie są bezpośrednio obsługiwane przez `CRectTracker` program, takie jak przyciąganie do siatki lub Zachowaj proporcje, można zaimplementować, zastępując tę funkcję.

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a> CRectTracker:: CRectTracker

Tworzy i inicjuje `CRectTracker` obiekt.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>Parametry

*lpSrcRect*<br/>
Współrzędne obiektu Rectangle.

*nStyle*<br/>
Określa styl `CRectTracker` obiektu. Obsługiwane są następujące style:

- `CRectTracker::solidLine` Użyj linii kryjącej dla obramowania prostokąta.

- `CRectTracker::dottedLine` Użyj linii kropkowanej dla obramowania prostokąta.

- `CRectTracker::hatchedBorder` Użyj wzorca kreskowanego dla obramowania prostokąta.

- `CRectTracker::resizeInside` Uchwyty zmiany rozmiaru znajdujące się wewnątrz prostokąta.

- `CRectTracker::resizeOutside` Uchwyty zmiany rozmiaru znajdujące się poza prostokątem.

- `CRectTracker::hatchInside` Wzorzec kreskowany obejmuje cały prostokąt.

### <a name="remarks"></a>Uwagi

Konstruktor domyślny inicjuje `CRectTracker` obiekt z wartościami z *lpSrcRect* i inicjuje inne rozmiary do domyślnych ustawień systemowych. Jeśli obiekt jest tworzony bez parametrów, `m_rect` `m_nStyle` elementy członkowskie danych i są niezainicjowane.

## <a name="crecttrackerdraw"></a><a name="draw"></a> CRectTracker::D RAW

Wywołaj tę funkcję, aby narysować zewnętrzne linie i wewnętrzny region prostokąta.

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Wskaźnik na kontekst urządzenia, na którym ma zostać narysowane Rysowanie.

### <a name="remarks"></a>Uwagi

Styl śledzenia określa sposób wykonywania rysowania. `CRectTracker`Aby uzyskać więcej informacji na temat dostępnych stylów, zobacz Konstruktor.

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a> CRectTracker::D rawTrackerRect

Wywoływane przez platformę, gdy pozycja modułu śledzącego została zmieniona w ramach `Track` funkcji lub `TrackRubberBand` .

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Parametry

*lpRect*<br/>
Wskaźnik do `RECT` , który zawiera prostokąt do rysowania.

*pWndClipTo*<br/>
Wskaźnik do okna do użycia w wycinku prostokąta.

*Domeny*<br/>
Wskaźnik na kontekst urządzenia, na którym ma zostać narysowane Rysowanie.

*pWnd*<br/>
Wskaźnik do okna, w którym nastąpi Rysowanie.

### <a name="remarks"></a>Uwagi

Implementacja domyślna wykonuje wywołanie do `CDC::DrawFocusRect` , który rysuje prostokąt kropkowany.

Zastąp tę funkcję, aby zapewnić różne opinie podczas operacji śledzenia.

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a> CRectTracker:: GetHandleMask

Struktura wywołuje tę funkcję elementu członkowskiego, aby uzyskać maskę dla uchwytów zmiany rozmiaru prostokąta.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Wartość zwracana

Maska `CRectTracker` uchwytów zmiany rozmiaru elementu.

### <a name="remarks"></a>Uwagi

Uchwyty zmiany rozmiaru są wyświetlane na bokach i rogach prostokąta i umożliwiają użytkownikowi kontrolowanie kształtu i rozmiaru prostokąta.

Prostokąt ma 8 dojść do zmiany rozmiaru 0-7. Każdy uchwyt zmiany rozmiaru jest reprezentowany przez bit w masce; wartość tego bitu to 2 ^ *n*, gdzie *n* jest numerem uchwytu zmiany rozmiaru. Bity 0-3 odpowiadają uchwytom zmiany rozmiaru, zaczynając od lewego górnego rogu. Bity 4-7 odpowiadają uchwytom zmiany rozmiaru po stronie, rozpoczynając od górnego przesunięcia w prawo. Na poniższej ilustracji przedstawiono uchwyty rozmiaru prostokąta oraz odpowiednie numery i wartości uchwytu zmiany rozmiaru:

![Zmień rozmiar numerów uchwytów](../../mfc/reference/media/vc35dp1.gif "Zmień rozmiar numerów uchwytów")

Domyślna implementacja funkcji `GetHandleMask` zwraca maskę bitów, aby pojawiły się uchwyty zmiany rozmiaru. Jeśli pojedynczy bit jest włączony, zostanie narysowany odpowiedni uchwyt zmiany rozmiaru.

Przesłoń tę funkcję elementu członkowskiego, aby ukryć lub pokazać wskazane uchwyty zmiany rozmiaru.

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a> CRectTracker:: GetTrueRect

Wywołaj tę funkcję, aby pobrać współrzędne prostokąta.

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Parametry

*lpTrueRect*<br/>
Wskaźnik do `RECT` struktury, która będzie zawierać współrzędne urządzenia `CRectTracker` obiektu.

### <a name="remarks"></a>Uwagi

Wymiary prostokąta obejmują wysokość i szerokość dowolnych uchwytów zmiany rozmiaru znajdujących się na zewnętrznym obramowaniu. Po powrocie *lpTrueRect* jest zawsze znormalizowany prostokąt we współrzędnych urządzenia.

## <a name="crecttrackerhittest"></a><a name="hittest"></a> CRectTracker:: HitTest

Wywołaj tę funkcję, aby dowiedzieć się, czy użytkownik przeprowadził obsługę zmiany rozmiaru.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Punkt we współrzędnych urządzenia do przetestowania.

### <a name="return-value"></a>Wartość zwracana

Zwracana wartość jest oparta na typie wyliczeniowym `CRectTracker::TrackerHit` i może mieć jedną z następujących wartości:

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 2,0

- `CRectTracker::hitTopRight` jedno

- `CRectTracker::hitBottomRight` dwóch

- `CRectTracker::hitBottomLeft` r.3

- `CRectTracker::hitTop` czwart

- `CRectTracker::hitRight` 5000

- `CRectTracker::hitBottom` ust

- `CRectTracker::hitLeft` 7

- `CRectTracker::hitMiddle` 0,8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a> CRectTracker:: m_nHandleSize

Rozmiar uchwytów zmiany rozmiaru (w pikselach) `CRectTracker` .

```
int m_nHandleSize;
```

### <a name="remarks"></a>Uwagi

Zainicjowany przy użyciu domyślnej wartości systemowej.

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a> CRectTracker:: m_rect

Bieżąca pozycja prostokąta (w pikselach).

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a> CRectTracker:: m_sizeMin

Minimalny rozmiar prostokąta.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Uwagi

Zarówno wartości domyślne, `cx` jak i `cy` są obliczane na podstawie domyślnej wartości systemowej szerokości obramowania. Ten element członkowski danych jest używany tylko przez `AdjustRect` funkcję członkowską.

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a> CRectTracker:: m_nStyle

Bieżący styl prostokąta.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Uwagi

Aby uzyskać listę możliwych stylów, zobacz [CRectTracker:: CRectTracker](#crecttracker) .

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a> CRectTracker:: NormalizeHit

Wywołaj tę funkcję, aby skonwertować potencjalnie odwróconą dojście.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Parametry

*nHandle*<br/>
Dojście wybrane przez użytkownika.

### <a name="return-value"></a>Wartość zwracana

Indeks znormalizowanego dojścia.

### <a name="remarks"></a>Uwagi

Gdy `CRectTracker::Track` lub `CRectTracker::TrackRubberBand` jest wywoływana z odwróceniem dozwolonym, istnieje możliwość odwrócenia prostokąta na osi x, osi y lub obu. W takim przypadku `HitTest` zwróci on uchwyty, które są również odwrócone w odniesieniu do prostokąta. Jest to nieodpowiedni do rysowania opinii o kursorach, ponieważ opinia zależy od położenia ekranu prostokąta, a nie od części struktury danych prostokąta, która zostanie zmodyfikowana.

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a> CRectTracker:: OnChangedRect

Wywoływane przez platformę, gdy prostokąt śledzenia został zmieniony podczas wywołania do `Track` .

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Parametry

*rectOld*<br/>
Zawiera stare współrzędne urządzenia dla `CRectTracker` obiektu.

### <a name="remarks"></a>Uwagi

W momencie wywołania tej funkcji wszystkie opinie narysowane za pomocą zostały `DrawTrackerRect` usunięte. Domyślna implementacja tej funkcji nic nie robi.

Zastąp tę funkcję, gdy chcesz wykonać dowolne akcje po zmianie rozmiaru prostokąta.

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a> CRectTracker:: SetCursor

Wywołaj tę funkcję, aby zmienić kształt kursora, gdy znajduje się on nad `CRectTracker` regionem obiektu.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskazuje okno, w którym znajduje się obecnie kursor.

*nHitTest*<br/>
Wyniki poprzedniego testu trafień z komunikatu WM_SETCURSOR.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli poprzednie trafienie dotyczyło prostokąta śledzenia; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję z wewnątrz funkcji okna, która obsługuje komunikat WM_SETCURSOR (zazwyczaj `OnSetCursor` ).

## <a name="crecttrackertrack"></a><a name="track"></a> CRectTracker:: Track

Wywołaj tę funkcję, aby wyświetlić interfejs użytkownika służący do zmiany rozmiarów prostokąta.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Obiekt okna, który zawiera prostokąt.

*moment*<br/>
Współrzędne urządzenia bieżącej pozycji myszy względem obszaru klienckiego.

*bAllowInvert*<br/>
W przypadku wartości TRUE prostokąt może być odwrócony wzdłuż osi x lub osi y. w przeciwnym razie FALSE.

*pWndClipTo*<br/>
Do okna, do którego zostaną nacięte operacje rysowania. Jeśli wartość jest równa NULL, *pWnd* jest używany jako prostokąt przycinania.

### <a name="return-value"></a>Wartość zwracana

Jeśli klawisz ESC zostanie wciśnięty, proces śledzenia zostanie zatrzymany, prostokąt przechowywany w module śledzącym nie zostanie zmieniony i zostanie zwrócony 0. Jeśli zmiana zostanie zatwierdzona, przenosząc mysz i zwolnisz lewy przycisk myszy, nowe położenie i/lub rozmiar są rejestrowane w prostokącie śledzenia i zwracany jest różny od zera.

### <a name="remarks"></a>Uwagi

Jest to zwykle wywoływane z wnętrza funkcji aplikacji, która obsługuje `WM_LBUTTONDOWN` komunikat (zazwyczaj `OnLButtonDown` ).

Ta funkcja przechwytuje mysz, dopóki użytkownik zwolni lewy przycisk myszy, naciśnie klawisz ESC lub naciśnie prawy przycisk myszy. Gdy użytkownik przesuwa wskaźnik myszy, opinia jest aktualizowana przez wywołanie `DrawTrackerRect` i `OnChangedRect` .

Jeśli *bAllowInvert* ma wartość true, prostokąt śledzenia może być odwrócony na osi x lub y.

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a> CRectTracker:: TrackRubberBand

Wywołaj tę funkcję, aby wybrać gumową grupę.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Obiekt okna, który zawiera prostokąt.

*moment*<br/>
Współrzędne urządzenia bieżącej pozycji myszy względem obszaru klienckiego.

*bAllowInvert*<br/>
W przypadku wartości TRUE prostokąt może być odwrócony wzdłuż osi x lub osi y. w przeciwnym razie FALSE.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli mysz została przeniesiona, a prostokąt nie jest pusty. w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jest on zazwyczaj wywoływany z wewnątrz funkcji aplikacji, która obsługuje komunikat WM_LBUTTONDOWN (zazwyczaj `OnLButtonDown` ).

Ta funkcja przechwytuje mysz, dopóki użytkownik zwolni lewy przycisk myszy, naciśnie klawisz ESC lub naciśnie prawy przycisk myszy. Gdy użytkownik przesuwa wskaźnik myszy, opinia jest aktualizowana przez wywołanie `DrawTrackerRect` i `OnChangedRect` .

Śledzenie jest przeprowadzane z opcją wyboru typu "kauczuk" w prawym dolnym rogu. W przypadku odwrócenia można zmienić rozmiar prostokąta, przeciągając je w górę i w lewo lub w dół i w prawo.

## <a name="see-also"></a>Zobacz też

[Przykładowe śledzenie MFC](../../overview/visual-cpp-samples.md)<br/>
[Przykład DRAWCLI MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleResizeBar](../../mfc/reference/coleresizebar-class.md)<br/>
[Klasa CRect](../../atl-mfc-shared/reference/crect-class.md)
