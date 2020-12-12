---
description: 'Dowiedz się więcej na temat: Klasa CGopherLocator'
title: Klasa CGopherLocator
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: f615ce6fbda150d923f6664acff207fdebdbba3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184026"
---
# <a name="cgopherlocator-class"></a>Klasa CGopherLocator

Pobiera "lokalizator" z serwera gopher, określa typ lokalizatora i sprawia, że lokalizator jest dostępny dla [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
> Klasy `CGopherConnection` ,, `CGopherFile` `CGopherFileFind` `CGopherLocator` i ich elementy członkowskie są przestarzałe, ponieważ nie działają na platformie Windows XP, ale będą nadal działały na wcześniejszych platformach.

## <a name="syntax"></a>Składnia

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Konstruuje `CGopherLocator` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CGopherLocator:: GetLocatorType](#getlocatortype)|Analizuje lokalizator Gopher i określa jego atrybuty.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CGopherLocator:: operator LPCTSTR](#operator_lpctstr)|Bezpośrednio uzyskuje dostęp do znaków przechowywanych w `CGopherLocator` obiekcie jako ciąg w stylu języka C.|

## <a name="remarks"></a>Uwagi

Aby można było pobrać informacje z tego serwera, aplikacja musi pobrać lokalizator serwera gopher. Gdy ma lokalizator, musi traktować lokalizator jako nieprzezroczysty token.

Każdy lokalizator gopher ma atrybuty, które określają typ znalezionego pliku lub serwera. Zobacz [GetLocatorType](#getlocatortype) , aby wyświetlić listę typów lokalizatorów gopher.

Aplikacja zwykle używa lokalizatora dla wywołań [CGopherFileFind:: FindFile —](../../mfc/reference/cgopherfilefind-class.md#findfile) w celu pobrania określonych informacji.

Aby dowiedzieć się więcej o `CGopherLocator` tym, jak działa z innymi klasami internetowymi MFC, zobacz artykuł [programowanie internetowe za pomocą usługi WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxinet. h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a> CGopherLocator::CGopherLocator

Ta funkcja członkowska jest wywoływana w celu utworzenia `CGopherLocator` obiektu.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parametry

*ref*<br/>
Odwołanie do `CGopherLocator` obiektu stałego.

### <a name="remarks"></a>Uwagi

Nie utworzysz `CGopherLocator` bezpośrednio obiektu. Zamiast tego wywołaj [CGopherConnection:: Islocatorer](../../mfc/reference/cgopherconnection-class.md#createlocator) , aby utworzyć i zwrócić wskaźnik do `CGopherLocator` obiektu.

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a> CGopherLocator:: GetLocatorType

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać typ lokalizatora.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parametry

*dwRef*<br/>
Odwołanie do typu DWORD, który będzie otrzymywał typ lokalizatora. Zobacz **uwagi** dotyczące tabeli typów lokalizatora.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0. Jeśli wywołanie nie powiedzie się, może zostać wywołana [wartość GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) funkcji Win32, aby określić przyczynę błędu.

### <a name="remarks"></a>Uwagi

Możliwe typy są następujące:

|Wartość|Znaczenie|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Plik tekstowy ASCII.|
|GOPHER_TYPE_DIRECTORY|Katalog dodatkowych elementów gopher.|
|GOPHER_TYPE_CSO|Serwer książki telefonicznej CSO.|
|GOPHER_TYPE_ERROR|Wskazuje warunek błędu.|
|GOPHER_TYPE_MAC_BINHEX|Plik systemu Macintosh w formacie BINHEX.|
|GOPHER_TYPE_DOS_ARCHIVE|Plik archiwum DOS.|
|GOPHER_TYPE_UNIX_UUENCODED|Plik UUENCODE.|
|GOPHER_TYPE_INDEX_SERVER|Serwer indeksu.|
|GOPHER_TYPE_TELNET|Serwer Telnet.|
|GOPHER_TYPE_BINARY|Plik binarny.|
|GOPHER_TYPE_REDUNDANT|Zduplikowany serwer. Informacje zawarte w ramach programu są duplikatem serwera podstawowego. Serwer podstawowy jest ostatnim wpisem katalogu, który nie miał GOPHER_TYPE_REDUNDANT typu.|
|GOPHER_TYPE_TN3270|Serwer protokołu TN3270.|
|GOPHER_TYPE_GIF|Plik graficzny GIF.|
|GOPHER_TYPE_IMAGE|Plik obrazu.|
|GOPHER_TYPE_BITMAP|Plik mapy bitowej.|
|GOPHER_TYPE_MOVIE|Plik filmu.|
|GOPHER_TYPE_SOUND|Plik dźwiękowy.|
|GOPHER_TYPE_HTML|Dokument HTML.|
|GOPHER_TYPE_PDF|Plik PDF.|
|GOPHER_TYPE_CALENDAR|Plik kalendarza.|
|GOPHER_TYPE_INLINE|Plik wbudowany.|
|GOPHER_TYPE_UNKNOWN|Typ elementu jest nieznany.|
|GOPHER_TYPE_ASK|Element Zażądaj i.|
|GOPHER_TYPE_GOPHER_PLUS|Element gopher +.|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a> CGopherLocator:: operator LPCTSTR

Ten przydatny operator rzutowania zapewnia wydajną metodę uzyskiwania dostępu do ciągu C zakończonych znakiem null zawartego w `CGopherLocator` obiekcie.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik znaku do danych ciągu.

### <a name="remarks"></a>Uwagi

Nie są kopiowane żadne znaki; zwracany jest tylko wskaźnik.

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)
