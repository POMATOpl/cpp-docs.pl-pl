---
description: 'Dowiedz się więcej na temat: Klasa CD2DBitmap'
title: Klasa CD2DBitmap
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: ab023caa92683b24098db1a03d081922e3dfd48b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227653"
---
# <a name="cd2dbitmap-class"></a>Klasa CD2DBitmap

Otoka dla ID2D1Bitmap.

## <a name="syntax"></a>Składnia

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Przeciążone. Konstruuje obiekt CD2DBitmap z HBITMAP.|
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Destruktor. Wywołuje się, gdy obiekt mapy bitowej D2D jest niszczony.|

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Przeciążone. Konstruuje obiekt CD2DBitmap.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Kopiuje określony region z określonej mapy bitowej do bieżącej mapy bitowej|
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Kopiuje określony region z pamięci do bieżącej mapy bitowej|
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Kopiuje określony region z określonego elementu docelowego renderowania do bieżącej mapy bitowej|
|[CD2DBitmap:: Create](#create)|Tworzy element CD2DBitmap. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmap::D Estroy](#destroy)|Niszczy obiekt CD2DBitmap. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBitmap::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DBitmap:: Get](#get)|Zwraca interfejs ID2D1Bitmap|
|[CD2DBitmap:: GetDPI](#getdpi)|Zwróć punkty na cal (DPI) mapy bitowej|
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Pobiera format pikseli i tryb alfa mapy bitowej|
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Zwraca rozmiar mapy bitowej w jednostkach zależnych od urządzenia (pikselach)|
|[CD2DBitmap:: GetSize](#getsize)|Zwraca rozmiar w pikselach niezależnych od urządzenia (DIP) mapy bitowej|
|[CD2DBitmap:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap::CommonInit](#commoninit)|Inicjuje obiekt|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap:: operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|Zwraca interfejs ID2D1Bitmap|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBitmap:: m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|Ma wartość TRUE, jeśli m_hBmpSrc powinna zostać zniszczona; w przeciwnym razie FALSE.|
|[CD2DBitmap:: m_hBmpSrc](#m_hbmpsrc)|Uchwyt mapy bitowej źródła.|
|[CD2DBitmap:: m_lpszType](#m_lpsztype)|Typ zasobu.|
|[CD2DBitmap:: m_pBitmap](#m_pbitmap)|Przechowuje wskaźnik do obiektu ID2D1Bitmap.|
|[CD2DBitmap:: m_sizeDest](#m_sizedest)|Rozmiar docelowy mapy bitowej.|
|[CD2DBitmap:: m_strPath](#m_strpath)|Ścieżka pliku Botmap.|
|[CD2DBitmap:: m_uiResID](#m_uiresid)|Identyfikator zasobu mapy bitowej.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a> CD2DBitmap:: ~ CD2DBitmap

Destruktor. Wywołuje się, gdy obiekt mapy bitowej D2D jest niszczony.

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a> CD2DBitmap:: Attach

Dołącza istniejący interfejs zasobów do obiektu.

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL.

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a> CD2DBitmap::CD2DBitmap

Konstruuje obiekt CD2DBitmap z zasobu.

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*uiResID*<br/>
Numer identyfikatora zasobu.

*lpszType*<br/>
Wskaźnik na ciąg zakończony znakiem null, który zawiera typ zasobu.

*o największej wielkości*<br/>
Rozmiar docelowy mapy bitowej.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

*lpszPath*<br/>
Wskaźnik na ciąg zakończony znakiem null, który zawiera nazwę pliku.

*hbmpSrc*<br/>
Dojście do mapy bitowej.

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a> CD2DBitmap::CommonInit

Inicjuje obiekt.

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a> CD2DBitmap::CopyFromBitmap

Kopiuje określony region z określonej mapy bitowej do bieżącej mapy bitowej.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametry

*pBitmap*<br/>
Mapa bitowa do skopiowania.

*destPoint*<br/>
W bieżącej mapie bitowej górny lewy róg obszaru, do którego jest kopiowany region określony przez srcRect.

*srcRect*<br/>
Obszar mapy bitowej do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a> CD2DBitmap::CopyFromMemory

Kopiuje określony region z pamięci do bieżącej mapy bitowej.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>Parametry

*srcData*<br/>
Dane do skopiowania.

*tonu*<br/>
Krok lub gęstość źródłowej mapy bitowej przechowywanej w srcData. Krok to liczba bajtów scanline (jeden wiersz pikseli w pamięci). Krok można obliczyć z następującej formuły: bajty o szerokości pikseli \* na piksel + dopełnienie pamięci.

*destRect*<br/>
W bieżącej mapie bitowej górny lewy róg obszaru, do którego jest kopiowany region określony przez srcRect.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a> CD2DBitmap::CopyFromRenderTarget

Kopiuje określony region z określonego obiektu docelowego renderowania do bieżącej mapy bitowej.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Obiekt docelowy renderowania zawierający region do skopiowania.

*destPoint*<br/>
W bieżącej mapie bitowej górny lewy róg obszaru, do którego jest kopiowany region określony przez srcRect.

*srcRect*<br/>
Obszar renderTarget do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dbitmapcreate"></a><a name="create"></a> CD2DBitmap:: Create

Tworzy element CD2DBitmap.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a> CD2DBitmap::D Estroy

Niszczy obiekt CD2DBitmap.

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a> CD2DBitmap::D etach

Odłącza interfejs zasobów od obiektu.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dbitmapget"></a><a name="get"></a> CD2DBitmap:: Get

Zwraca interfejs ID2D1Bitmap.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Bitmap lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a> CD2DBitmap:: GetDPI

Zwróć punkty na cal (DPI) mapy bitowej.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Wartość zwracana

Pozioma i pionowa wartość DPI mapy bitowej.

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a> CD2DBitmap::GetPixelFormat

Pobiera format pikseli i tryb alfa mapy bitowej

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Wartość zwracana

Format pikseli i tryb alfa mapy bitowej.

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a> CD2DBitmap::GetPixelSize

Zwraca rozmiar mapy bitowej w jednostkach zależnych od urządzenia (pikselach).

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar mapy bitowej (w pikselach).

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a> CD2DBitmap:: GetSize

Zwraca rozmiar mapy bitowej w pikselach niezależnych od urządzenia (DIP).

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar mapy bitowej (w wartości DIP).

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a> CD2DBitmap:: IsValid

Sprawdza poprawność zasobów.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a> CD2DBitmap:: m_bAutoDestroyHBMP

Ma wartość TRUE, jeśli m_hBmpSrc powinna zostać zniszczona; w przeciwnym razie FALSE.

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a> CD2DBitmap:: m_hBmpSrc

Uchwyt mapy bitowej źródła.

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a> CD2DBitmap:: m_lpszType

Typ zasobu.

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmap:: m_pBitmap

Przechowuje wskaźnik do obiektu ID2D1Bitmap.

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a> CD2DBitmap:: m_sizeDest

Rozmiar docelowy mapy bitowej.

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a> CD2DBitmap:: m_strPath

Ścieżka pliku Botmap.

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a> CD2DBitmap:: m_uiResID

Identyfikator zasobu mapy bitowej.

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a> CD2DBitmap:: operator ID2D1Bitmap *

Zwraca interfejs ID2D1Bitmap

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Bitmap lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
