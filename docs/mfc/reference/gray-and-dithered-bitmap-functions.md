---
description: 'Dowiedz się więcej o: szare i wyszarzone funkcje map bitowych'
title: Funkcje szarych i symulowanych map bitowych
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: 20391f0ee7227827e1d9d6e18c2379be1fd43612
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219736"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Funkcje szarych i symulowanych map bitowych

**Szare funkcje mapy bitowej**

MFC udostępnia dwie funkcje do nadawania mapy bitowej wyglądu wyłączonej kontrolki.

![Porównanie wersji ikon szarych i oryginalnych](../../mfc/reference/media/vcgraybitmap.gif "Porównanie wersji ikon szarych i oryginalnych")

|Nazwa|Opis|
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Rysuje szarą wersję mapy bitowej.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Kopiuje szarą wersję mapy bitowej.|

**Funkcje mapy bitowej**

MFC udostępnia również dwie funkcje do zastępowania tła mapy bitowej ze wzorcem.

![Porównanie wersji ikon z podaną i wersją](../../mfc/reference/media/vcditheredbitmap.gif "Porównanie wersji ikon z podaną i wersją")

|Nazwa|Opis|
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Rysuje mapę bitową z tłem w tle.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Kopiuje mapę bitową z tłem w tle.|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a> AfxDrawGrayBitmap

Rysuje szarą wersję mapy bitowej.

```cpp
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Wskazuje docelowy kontroler domeny.

*x*<br/>
Docelowa Współrzędna x.

*Y*<br/>
Współrzędna y docelowej.

*rSrc*<br/>
Źródłowa Mapa bitowa.

*crBackground*<br/>
Nowy kolor tła (zwykle szary, taki jak COLOR_MENU).

### <a name="remarks"></a>Uwagi

Mapa bitowa narysowana przy użyciu `AfxDrawGrayBitmap` będzie mieć wygląd wyłączonej kontrolki.

![Porównanie wersji ikon szarych i oryginalnych](../../mfc/reference/media/vcgraybitmap.gif "Porównanie wersji ikon szarych i oryginalnych")

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a> AfxGetGrayBitmap

Kopiuje szarą wersję mapy bitowej.

```cpp
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametry

*rSrc*<br/>
Źródłowa Mapa bitowa.

*pDest*<br/>
Docelowa Mapa bitowa.

*crBackground*<br/>
Nowy kolor tła (zwykle szary, taki jak COLOR_MENU).

### <a name="remarks"></a>Uwagi

Mapa bitowa skopiowana z `AfxGetGrayBitmap` będzie mieć wygląd wyłączonej kontrolki.

![Porównanie wersji ikon szarych i oryginalnych](../../mfc/reference/media/vcgraybitmap.gif "Porównanie wersji ikon szarych i oryginalnych")

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a> AfxDrawDitheredBitmap

Rysuje mapę bitową, zastępując jej tło wzorcem (pionem).

```cpp
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Wskazuje docelowy kontroler domeny.

*x*<br/>
Docelowa Współrzędna x.

*Y*<br/>
Współrzędna y docelowej.

*rSrc*<br/>
Źródłowa Mapa bitowa.

*cr1*<br/>
Jeden z dwóch kolorów symulowania, zazwyczaj biały.

*cr2*<br/>
Inny kolor symulowania, zazwyczaj jasnoszary (COLOR_MENU).

### <a name="remarks"></a>Uwagi

Źródłowa Mapa bitowa jest rysowana na docelowym kontrolerze domeny przy użyciu wzorca z dwoma kolorami (*cr1* i *CR2*), zastępując tło mapy bitowej. Tło źródłowej mapy bitowej jest definiowane jako białe piksele i wszystkie piksele pasujące do koloru piksela w lewym górnym rogu mapy bitowej.

![Porównanie wersji ikon z podaną i wersją](../../mfc/reference/media/vcditheredbitmap.gif "Porównanie wersji ikon z podaną i wersją")

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a> AfxGetDitheredBitmap

Kopiuje mapę bitową, zastępując jej tło wzorcem (pionem).

```cpp
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametry

*rSrc*<br/>
Źródłowa Mapa bitowa.

*pDest*<br/>
Docelowa Mapa bitowa.

*cr1*<br/>
Jeden z dwóch kolorów symulowania, zazwyczaj biały.

*cr2*<br/>
Inny kolor symulowania, zazwyczaj jasnoszary (COLOR_MENU).

### <a name="remarks"></a>Uwagi

Źródłowa Mapa bitowa jest kopiowana do docelowej mapy bitowej przy użyciu wzorca z dwoma kolorami (*cr1* i *CR2*), zastępując tło źródłowej mapy bitowej. Tło źródłowej mapy bitowej jest definiowane jako białe piksele i wszystkie piksele pasujące do koloru piksela w lewym górnym rogu mapy bitowej.

![Porównanie wersji ikon z podaną i wersją](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)
