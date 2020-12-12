---
description: 'Dowiedz się więcej na temat: Klasa CPictureHolder'
title: Klasa CPictureHolder
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: 47eacb66191e21b300aaa0d06bc23155fabaf651
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301480"
---
# <a name="cpictureholder-class"></a>Klasa CPictureHolder

Implementuje właściwość obrazu, która umożliwia użytkownikowi wyświetlanie obrazu w kontrolce.

## <a name="syntax"></a>Składnia

```
class CPictureHolder
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|Konstruuje `CPictureHolder` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPictureHolder:: IsEmpty](#createempty)|Tworzy pusty `CPictureHolder` obiekt.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Tworzy `CPictureHolder` obiekt z mapy bitowej.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|Tworzy `CPictureHolder` obiekt na podstawie ikony.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Tworzy `CPictureHolder` obiekt z metapliku.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Pobiera ciąg wyświetlany w przeglądarce właściwości kontenera kontrolek.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Zwraca `CPictureHolder` `IDispatch` interfejs obiektu.|
|[CPictureHolder:: GetType](#gettype)|Informuje, czy `CPictureHolder` obiekt jest mapą bitową, metaplikiem, czy ikoną.|
|[CPictureHolder:: Render](#render)|Renderuje obraz.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Ustawia `CPictureHolder` `IDispatch` interfejs obiektu.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CPictureHolder:: m_pPict](#m_ppict)|Wskaźnik do obiektu obrazu.|

## <a name="remarks"></a>Uwagi

`CPictureHolder` nie ma klasy bazowej.

Mając Właściwość obrazu podstawowego, deweloper może określić mapę bitową, ikonę lub metaplik do wyświetlenia.

Aby uzyskać informacje na temat tworzenia niestandardowych właściwości obrazu, zobacz artykuł [kontrolki ActiveX MFC: używanie obrazów w kontrolce ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CPictureHolder`

## <a name="requirements"></a>Wymagania

**Nagłówek:** 'afxctl. h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a> CPictureHolder::CPictureHolder

Konstruuje `CPictureHolder` obiekt.

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a> CPictureHolder:: IsEmpty

Tworzy pusty `CPictureHolder` obiekt i łączy go z `IPicture` interfejsem.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został pomyślnie utworzony; w przeciwnym razie 0.

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a> CPictureHolder::CreateFromBitmap

Używa mapy bitowej do zainicjowania obiektu obrazu w `CPictureHolder` .

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametry

*idResource*<br/>
Identyfikator zasobu dla zasobu mapy bitowej.

*pBitmap*<br/>
Wskaźnik do obiektu [CBitmap](../../mfc/reference/cbitmap-class.md) .

*pPal*<br/>
Wskaźnik do obiektu [CPalette](../../mfc/reference/cpalette-class.md) .

*bTransferOwnership*<br/>
Wskazuje, czy obiekt obrazu przejdzie na własność obiektów mapy bitowej i palety.

*hbm*<br/>
Dojście do mapy bitowej, z której `CPictureHolder` tworzony jest obiekt.

*hpal*<br/>
Dojście do palety używanej do renderowania mapy bitowej.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został pomyślnie utworzony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli *bTransferOwnership* ma wartość true, wywołujący nie powinien używać obiektu mapy bitowej ani palety w dowolny sposób po powrocie tego wywołania. Jeśli *bTransferOwnership* ma wartość false, obiekt wywołujący jest odpowiedzialny za upewnienie się, że mapa bitowa i obiekty palety pozostają prawidłowe dla okresu istnienia obiektu obrazu.

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a> CPictureHolder::CreateFromIcon

Używa ikony, aby zainicjować obiekt obrazu w `CPictureHolder` .

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametry

*idResource*<br/>
Identyfikator zasobu dla zasobu mapy bitowej.

*hIcon*<br/>
Dojście do ikony, z której `CPictureHolder` tworzony jest obiekt.

*bTransferOwnership*<br/>
Wskazuje, czy obiekt obrazu będzie przejmować na własność obiekt ikony.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został pomyślnie utworzony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli *bTransferOwnership* ma wartość true, obiekt wywołujący nie powinien używać obiektu Icon w żaden sposób po powrocie tego wywołania. Jeśli *bTransferOwnership* ma wartość false, obiekt wywołujący jest odpowiedzialny za upewnienie się, że obiekt ikony pozostaje prawidłowy dla okresu istnienia obiektu obrazu.

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a> CPictureHolder::CreateFromMetafile

Używa metapliku do zainicjowania obiektu obrazu w `CPictureHolder` .

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametry

*hmf*<br/>
Dojście do metapliku użytego do utworzenia `CPictureHolder` obiektu.

*xExt*<br/>
X zasięg obrazu.

*yExt*<br/>
Zakres Y obrazu.

*bTransferOwnership*<br/>
Wskazuje, czy obiekt obrazu będzie przejmować własność obiektu metaplik.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został pomyślnie utworzony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli *bTransferOwnership* ma wartość true, obiekt wywołujący nie powinien używać obiektu metapliku w dowolny sposób po powrocie tego wywołania. Jeśli *bTransferOwnership* ma wartość false, obiekt wywołujący jest odpowiedzialny za upewnienie się, że obiekt metapliku pozostaje prawidłowy dla okresu istnienia obiektu obrazu.

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a> CPictureHolder::GetDisplayString

Pobiera ciąg, który jest wyświetlany w przeglądarce właściwości kontenera.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametry

*strValue*<br/>
Odwołanie do [CString](../../atl-mfc-shared/reference/cstringt-class.md) , która ma przechowywać ciąg wyświetlania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli ciąg został pomyślnie pobrany; w przeciwnym razie 0.

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a> CPictureHolder::GetPictureDispatch

Ta funkcja zwraca wskaźnik do `CPictureHolder` `IPictureDisp` interfejsu obiektu.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CPictureHolder` `IPictureDisp` interfejsu obiektu.

### <a name="remarks"></a>Uwagi

Obiekt wywołujący musi wywołać `Release` na tym wskaźniku po jego zakończeniu.

## <a name="cpictureholdergettype"></a><a name="gettype"></a> CPictureHolder:: GetType

Wskazuje, czy obraz jest mapą bitową, metaplikiem lub ikoną.

```
short GetType();
```

### <a name="return-value"></a>Wartość zwracana

Wartość wskazująca typ obrazu. Możliwe wartości i ich znaczenie są następujące:

|Wartość|Znaczenie|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` Obiekt jest unititialized.|
|PICTYPE_NONE|`CPictureHolder` Obiekt jest pusty.|
|PICTYPE_BITMAP|Obraz jest mapą bitową.|
|PICTYPE_METAFILE|Obraz jest metaplikiem.|
|PICTYPE_ICON|Obraz jest ikoną.|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a> CPictureHolder:: m_pPict

Wskaźnik do `CPictureHolder` `IPicture` interfejsu obiektu.

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a> CPictureHolder:: Render

Renderuje obraz w prostokącie, do którego odwołuje się *rcRender*.

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
Wskaźnik do kontekstu wyświetlania, w którym obraz ma być renderowany.

*rcRender*<br/>
Prostokąt, w którym ma być renderowany obraz.

*rcWBounds*<br/>
Prostokąt reprezentujący prostokąt ograniczający obiekt, który renderuje obraz. W przypadku kontrolki ten prostokąt jest parametrem *rcBounds* przesłanym do przesłonięcia [COleControl:: OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a> CPictureHolder::SetPictureDispatch

Łączy `CPictureHolder` obiekt z `IPictureDisp` interfejsem.

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Parametry

*pDisp*<br/>
Wskaźnik do nowego `IPictureDisp` interfejsu.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CFontHolder](../../mfc/reference/cfontholder-class.md)
