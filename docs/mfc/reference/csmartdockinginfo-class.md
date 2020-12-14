---
description: 'Dowiedz się więcej na temat: Klasa CSmartDockingInfo'
title: Klasa CSmartDockingInfo
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: 290f9eef208ceed425739ab26e7811c04309e057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345137"
---
# <a name="csmartdockinginfo-class"></a>Klasa CSmartDockingInfo

Definiuje wygląd inteligentnych znaczników dokowania.

## <a name="syntax"></a>Składnia

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|Konstruktor domyślny.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSmartDockingInfo:: CopyTo](#copyto)|Kopiuje bieżące inteligentne dokowanie parametrów informacji do podanego obiektu [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) .|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CSmartDockingInfo:: m_bUseThemeColorInShading](#m_busethemecolorinshading)|Określa, czy bieżący kolor motywu ma być używany, gdy struktura Wyświetla inteligentne znaczniki dokowania.|
|[CSmartDockingInfo:: m_clrBaseBackground](#m_clrbasebackground)|Określa podstawowy kolor tła znaczników dokowania inteligentnego.|
|[CSmartDockingInfo:: m_clrToneDest](#m_clrtonedest)|Określa kolor zastępujący `m_clrToneSrc` mapy bitowe znaczników dokowania inteligentnego.|
|[CSmartDockingInfo:: m_clrToneSrc](#m_clrtonesrc)|Określa kolor map inteligentnych znaczników dokowania.|
|[CSmartDockingInfo:: m_clrTransparent](#m_clrtransparent)|Określa kolor inteligentnych map dokujących znaczników, gdy są one przezroczyste.|
|[CSmartDockingInfo:: m_nCentralGroupOffset](#m_ncentralgroupoffset)|Określa przesunięcie centralną grupę znaczników dokowania inteligentnej z granic prostokąta grupy centralnej.|
|[CSmartDockingInfo:: m_sizeTotal](#m_sizetotal)|Określa całkowity rozmiar wszystkich znaczników dokowania inteligentnej w grupie.|
|[CSmartDockingInfo:: m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Definiuje identyfikatory zasobów map bitowych, które są używane przez platformę do inteligentnych znaczników dokowania, które nie są wyróżnione.|
|[CSmartDockingInfo:: m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Definiuje identyfikatory zasobów map bitowych, które są używane przez platformę do podświetlania inteligentnych znaczników dokowania.|

## <a name="remarks"></a>Uwagi

Struktura obsługuje wewnętrznie inteligentne znaczniki dokowania. Na poniższej ilustracji przedstawiono standardowe inteligentne znaczniki dokowania:

![Standardowe znaczniki dla dokowania inteligentnego](../../mfc/reference/media/nextsdmarkers.png "Standardowe znaczniki dla dokowania inteligentnego")

Na tym rysunku obraz po lewej stronie zawiera znacznik inteligentnego zadokowania grupy centralnej, który nie ma zadokowanych kart. Obraz w środku przedstawia znacznik inteligentnego dokowania prawej krawędzi. Obraz po prawej stronie zawiera znacznik inteligentnego zadokowania grupy centralnej, który ma zadokowane na karcie. Znacznik inteligentnego dokowania grupy centralnej ma główną mapę bitową i pięć map inteligentnych znaczników dokowania.

Można dostosować następujące parametry inteligentnych znaczników dokowania:

- Kolor. Na przykład, można zamienić niebieski kolor znaczników na rysunku z dowolnym kolorem zdefiniowanym przez użytkownika.

- Kolor przezroczystości.

- Przesunięcie inteligentnego znacznika dokowania w grupie centralnej z obramowania prostokąta obwiedni.

- Główna Mapa bitowa reprezentująca grupę centralną.

- Mapy bitowe, które reprezentują regularne i wyróżnione inteligentne znaczniki dokowania.

Na poniższej ilustracji przedstawiono przykład inteligentnych znaczników dokowania, które zostały dostosowane:

![Niestandardowe znaczniki dla dokowania inteligentnego](../../mfc/reference/media/nextsdmarkerscustom.png "Niestandardowe znaczniki dla dokowania inteligentnego")

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxDockingManager. h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a> CSmartDockingInfo:: CopyTo

Kopiuje bieżące inteligentne parametry dokowania do podanego obiektu [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) .

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Parametry

*params*<br/>
określoną Obiekt typu `CSmartDockingInfo` , który jest wypełniany bieżącymi inteligentnymi parametrami dokowania.

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a> CSmartDockingInfo:: m_bUseThemeColorInShading

Określa, czy bieżący kolor motywu ma być używany, gdy struktura Wyświetla inteligentne znaczniki dokowania.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>Uwagi

Jeśli wartość jest równa TRUE, znaczniki są rysowane przy użyciu bieżącego koloru motywu; w przeciwnym razie znaczniki są rysowane z jasnoniebieskim kolorem.

Wartość domyślna to FALSE.

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a> CSmartDockingInfo:: m_clrBaseBackground

Określa podstawowy kolor tła znaczników dokowania inteligentnego.

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a> CSmartDockingInfo:: m_clrToneDest

Określa kolor, który zostanie zamieniony `m_clrToneSrc` na mapy bitowe znaczników dokowania inteligentnego.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>Uwagi

Ustaw tę wartość, aby programowo zmienić kolor map bitowych znaczników. Na przykład jeśli chcesz zmienić kolor znaczników standardowych dostarczonych z platformą, ustaw tę wartość na żądany kolor. Domyślnie [CSmartDockingInfo:: m_clrToneSrc](#m_clrtonesrc) jest ustawiona na RGB (61, 123, 241) (kolor bluish).

Aby zmienić kolor znaczników niestandardowych, należy określić zarówno `m_clrToneDest` , jak i `m_clrToneSrc` .

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a> CSmartDockingInfo:: m_clrToneSrc

Określa kolor map inteligentnych znaczników dokowania.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>Uwagi

Ustaw tę wartość tylko wtedy, gdy chcesz zastąpić kolor niestandardowej mapy bitowej innym kolorem. Nie trzeba ustawiać tej wartości w przypadku zmiany koloru znacznika standardowego (dostarczonego przez platformę).

Użyj `(COLORREF)-1` , aby opuścić pustą grupę inteligentnych dokowania.

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a> CSmartDockingInfo:: m_clrTransparent

Określa kolor inteligentnych map dokujących znaczników, gdy są one przezroczyste.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>Uwagi

Należy ustawić tę wartość, gdy w grupie dokującej są wyświetlane znaczniki niestandardowe i niestandardowe mapy bitowe.

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a> CSmartDockingInfo:: m_nCentralGroupOffset

Określa przesunięcie między centralną grupą znaczników dokowania inteligentnej a granicami prostokąta grupy centralnej.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>Uwagi

Określ tę wartość, jeśli chcesz zmienić domyślne przesunięcie między znacznikami niestandardowymi i granicami centralnej grupy znaczników dokowania inteligentnego. Domyślne przesunięcie to 5 pikseli.

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a> CSmartDockingInfo:: m_sizeTotal

Określa łączny rozmiar prostokąta ograniczającego, który zawiera wszystkie inteligentne znaczniki dokowania w grupie centralnej.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>Uwagi

Ustaw `m_sizeTotal` rozmiar prostokąta ograniczenia w znaczniku grupy centralnej. Musisz określić tę wartość, jeśli używasz niestandardowych map bitowych dla znaczników.

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a> CSmartDockingInfo:: m_uiMarkerBmpResID

Definiuje identyfikatory zasobów map bitowych, które są używane dla niewyróżnionych niestandardowych znaczników dokowania inteligentnego.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Uwagi

Wypełnij tę tablicę identyfikatorami zasobów Bitmap reprezentujących inteligentne znaczniki dokowania. AFX_SD_MARKERS_NUM jest obecnie zdefiniowany jako 5. Należy wypełnić tablicę w następujący sposób:

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a> CSmartDockingInfo:: m_uiMarkerLightBmpResID

Definiuje identyfikatory zasobów map bitowych, które są używane dla wyróżnionych niestandardowych znaczników dokowania inteligentnego.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>Uwagi

Wypełnij tę tablicę identyfikatorami zasobów map bitowych reprezentujących wyróżnione inteligentne znaczniki dokowania. AFX_SD_MARKERS_NUM jest obecnie zdefiniowany jako 5. Należy wypełnić tablicę w następujący sposób:

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)
