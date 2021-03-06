---
description: 'Dowiedz się więcej na temat: Klasa CFileFind'
title: Klasa CFileFind
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: d47c45ac86386a6748ca212c569aeef568ca2a8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184507"
---
# <a name="cfilefind-class"></a>Klasa CFileFind

Wykonuje wyszukiwanie plików lokalnych i jest klasą bazową dla [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) i [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), która wykonuje wyszukiwania plików internetowych.

## <a name="syntax"></a>Składnia

```
class CFileFind : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|Konstruuje `CFileFind` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileFind:: Close](#close)|Zamyka żądanie wyszukiwania.|
|[CFileFind:: FindFile —](#findfile)|Wyszukuje określoną nazwę pliku w katalogu.|
|[CFileFind::FindNextFile](#findnextfile)|Kontynuuje wyszukiwanie plików od poprzedniego wywołania do [FindFile —](#findfile).|
|[CFileFind::GetCreationTime](#getcreationtime)|Pobiera czas utworzenia pliku.|
|[CFileFind:: GetFileName](#getfilename)|Pobiera nazwę, łącznie z rozszerzeniem, znalezionego pliku|
|[CFileFind:: GetFilePath](#getfilepath)|Pobiera pełną ścieżkę znalezionego pliku.|
|[CFileFind::GetFileTitle](#getfiletitle)|Pobiera tytuł znalezionego pliku. Tytuł nie zawiera rozszerzenia.|
|[CFileFind::GetFileURL](#getfileurl)|Pobiera adres URL, łącznie z ścieżką pliku znalezionego pliku.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Pobiera godzinę ostatniego dostępu do pliku.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Pobiera czas ostatniej zmiany i zapisania pliku.|
|[CFileFind:: GetLength](#getlength)|Pobiera długość znalezionego pliku w bajtach.|
|[CFileFind:: GetRoot](#getroot)|Pobiera katalog główny znalezionego pliku.|
|[CFileFind:: IsArchived](#isarchived)|Określa, czy znaleziony plik jest archiwizowany.|
|[CFileFind:: issprężony](#iscompressed)|Określa, czy znaleziony plik jest skompresowany.|
|[CFileFind:: IsDirectory](#isdirectory)|Określa, czy znaleziony plik jest katalogiem.|
|[CFileFind:: iskropek](#isdots)|Określa, czy nazwa znalezionego pliku ma nazwę "." lub "..", co oznacza, że jest w rzeczywistości katalogiem.|
|[CFileFind:: IsHidden](#ishidden)|Określa, czy znaleziony plik jest ukryty.|
|[CFileFind:: isnormal](#isnormal)|Określa, czy znaleziony plik jest normalny (innymi słowy, nie ma innych atrybutów).|
|[CFileFind:: IsReadOnly](#isreadonly)|Określa, czy znaleziony plik jest tylko do odczytu.|
|[CFileFind:: IsSystem](#issystem)|Określa, czy znaleziony plik jest plikiem systemowym.|
|[CFileFind:: IsTemporary](#istemporary)|Określa, czy znaleziony plik jest tymczasowy.|
|[CFileFind::MatchesMask](#matchesmask)|Wskazuje żądane atrybuty pliku, który ma zostać znaleziony.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|Zamyka plik określony przez bieżące dojście wyszukiwania.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CFileFind:: m_pTM](#m_ptm)|Wskaźnik do `CAtlTransactionManager` obiektu.|

## <a name="remarks"></a>Uwagi

`CFileFind` obejmuje funkcje członkowskie, które rozpoczynają wyszukiwanie, odszukają plik i zwracają tytuł, nazwę lub ścieżkę pliku. W przypadku wyszukiwania w Internecie funkcja członkowska [GetFileURL](#getfileurl) zwraca adres URL pliku.

`CFileFind` jest klasą bazową dla dwóch innych klas MFC zaprojektowanych do wyszukiwania określonych typów serwerów: `CGopherFileFind` działa w szczególności z serwerami Gopher i `CFtpFileFind` działa w szczególności z serwerami FTP. Razem te trzy klasy zapewniają bezproblemowe mechanizmy klienta do znajdowania plików, niezależnie od protokołu serwerowego, typu pliku lub lokalizacji na komputerze lokalnym lub serwerze zdalnym.

Poniższy kod wylicza wszystkie pliki w bieżącym katalogu, drukując nazwę każdego pliku:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Aby zachować przykład prosty, ten kod używa klasy standardowej biblioteki języka C++ `cout` . `cout`Wiersz może zostać zastąpiony wywołaniem, na `CListBox::AddString` przykład w programie z graficznym interfejsem użytkownika.

Aby uzyskać więcej informacji na temat sposobu użycia `CFileFind` i innych klas WinInet, zobacz artykuł [programowanie internetowe za pomocą usługi WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a> CFileFind::CFileFind

Ta funkcja członkowska jest wywoływana, gdy `CFileFind` obiekt jest skonstruowany.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametry

*pTM*<br/>
Wskaźnik do obiektu CAtlTransactionManager

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindclose"></a><a name="close"></a> CFileFind:: Close

Wywołaj tę funkcję elementu członkowskiego, aby zakończyć wyszukiwanie, zresetuj kontekst i zwolnij wszystkie zasoby.

```cpp
void Close();
```

### <a name="remarks"></a>Uwagi

Po wywołaniu `Close` nie trzeba tworzyć nowego `CFileFind` wystąpienia przed wywołaniem [FindFile —](#findfile) , aby rozpocząć nowe wyszukiwanie.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a> CFileFind::CloseContext

Zamyka plik określony przez bieżące dojście wyszukiwania.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Uwagi

Zamyka plik określony przez bieżącą wartość dojścia wyszukiwania. Zastąp tę funkcję, aby zmienić zachowanie domyślne.

Musisz wywołać funkcje [FindFile —](#findfile) lub [FindNextFile](#findnextfile) co najmniej raz, aby pobrać prawidłowe dojście wyszukiwania. `FindFile`Funkcje i `FindNextFile` używają uchwytu wyszukiwania do lokalizowania plików o nazwach zgodnych z podaną nazwą.

## <a name="cfilefindfindfile"></a><a name="findfile"></a> CFileFind:: FindFile —

Wywołaj tę funkcję elementu członkowskiego, aby otworzyć wyszukiwanie plików.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parametry

*pstrName*<br/>
Wskaźnik do ciągu zawierającego nazwę pliku do znalezienia. W przypadku przekazania wartości NULL dla *pstrName*, `FindFile` czy jest to symbol wieloznaczny (*. \* ).

*dwUnused*<br/>
Zarezerwowane do udostępniania `FindFile` polimorficznych klas pochodnych. Musi mieć wartość 0.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0. Aby uzyskać rozszerzone informacje o błędzie, wywołaj [wartość GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)funkcji Win32.

### <a name="remarks"></a>Uwagi

Po wywołaniu `FindFile` , aby rozpocząć wyszukiwanie plików, wywołaj [FindNextFile](#findnextfile) , aby pobrać kolejne pliki. Musisz wywołać `FindNextFile` co najmniej raz przed wywołaniem dowolnej z następujących funkcji składowych atrybutów:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength —](#getlength)

- [Operacja GetRoot](#getroot)

- [Isarchiwalny](#isarchived)

- [Iskompresowane](#iscompressed)

- [IsDirectory](#isdirectory)

- [Iskropek](#isdots)

- [IsHidden](#ishidden)

- [Isnormal —](#isnormal)

- [IsReadOnly](#isreadonly)

- [Określonej właściwości IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: IsDirectory](#isdirectory).

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a> CFileFind::FindNextFile

Wywołaj tę funkcję elementu członkowskiego, aby kontynuować wyszukiwanie plików z poprzedniego wywołania do [FindFile —](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli istnieje więcej plików; zero, jeśli znaleziony plik jest ostatnim z nich w katalogu lub wystąpił błąd. Aby uzyskać rozszerzone informacje o błędzie, wywołaj [wartość GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)funkcji Win32. Jeśli znaleziony plik to ostatni plik w katalogu lub nie można znaleźć pasujących plików, `GetLastError` Funkcja zwraca ERROR_NO_MORE_FILES.

### <a name="remarks"></a>Uwagi

Musisz wywołać `FindNextFile` co najmniej raz przed wywołaniem dowolnej z następujących funkcji składowych atrybutów:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength —](#getlength)

- [Operacja GetRoot](#getroot)

- [Isarchiwalny](#isarchived)

- [Iskompresowane](#iscompressed)

- [IsDirectory](#isdirectory)

- [Iskropek](#isdots)

- [IsHidden](#ishidden)

- [Isnormal —](#isnormal)

- [IsReadOnly](#isreadonly)

- [Określonej właściwości IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile` Zawija funkcję Win32 [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew).

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: IsDirectory](#isdirectory).

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a> CFileFind::GetCreationTime

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać godzinę utworzenia określonego pliku.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametry

*pTimeStamp*<br/>
Wskaźnik do struktury [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) zawierającej czas utworzenia pliku.

*refTime*<br/>
Odwołanie do obiektu [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; 0, jeśli nie powiodło się. `GetCreationTime` Zwraca wartość 0 tylko wtedy, gdy [FindNextFile](#findnextfile) nigdy nie został wywołany dla tego `CFileFind` obiektu.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetCreationTime` .

> [!NOTE]
> Nie wszystkie systemy plików używają tej samej semantyki do implementowania sygnatury czasowej zwracanej przez tę funkcję. Ta funkcja może zwracać tę samą wartość zwracaną przez inne funkcje sygnatur czasowych, jeśli podstawowy system plików lub serwer nie obsługuje zachowywania atrybutu czasu. Zapoznaj się ze strukturą [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , aby uzyskać informacje na temat formatów czasu. W niektórych systemach operacyjnych zwrócony czas jest w strefie czasowej lokalnej dla komputera, w którym znajduje się plik. Aby uzyskać więcej informacji, zobacz Interfejs API Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a> CFileFind:: GetFileName

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać nazwę znalezionego pliku.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa ostatnio znalezionego pliku.

### <a name="remarks"></a>Uwagi

Przed wywołaniem metody GetFileName należy wywołać [FindNextFile](#findnextfile) co najmniej raz.

`GetFileName` jest jedną z trzech `CFileFind` funkcji Członkowskich, które zwracają część nazwy pliku. Na poniższej liście opisano trzy i różnice między nimi:

- `GetFileName` Zwraca nazwę pliku, łącznie z rozszerzeniem. Na przykład, wywołanie `GetFileName` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca nazwę pliku *myfile.txt*.

- [GetFilePath](#getfilepath) zwraca całą ścieżkę do pliku. Na przykład wywołanie `GetFilePath` wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca ścieżkę pliku *c:\myhtml\myfile.txt*.

- [GetFileTitle](#getfiletitle) zwraca nazwę pliku, z wyłączeniem rozszerzenia pliku. Na przykład, wywołanie `GetFileTitle` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca tytuł pliku. 

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a> CFileFind:: GetFilePath

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać pełną ścieżkę do określonego pliku.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Wartość zwracana

Ścieżka do określonego pliku.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetFilePath` .

`GetFilePath` jest jedną z trzech `CFileFind` funkcji Członkowskich, które zwracają część nazwy pliku. Na poniższej liście opisano trzy i różnice między nimi:

- [GetFileName](#getfilename) zwraca nazwę pliku, łącznie z rozszerzeniem. Na przykład, wywołanie `GetFileName` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca nazwę pliku *myfile.txt*.

- `GetFilePath` zwraca całą ścieżkę do pliku. Na przykład wywołanie `GetFilePath` wygenerowania komunikatu użytkownika dotyczącego pliku `c:\myhtml\myfile.txt` zwraca ścieżkę pliku `c:\myhtml\myfile.txt` .

- [GetFileTitle](#getfiletitle) zwraca nazwę pliku, z wyłączeniem rozszerzenia pliku. Na przykład, wywołanie `GetFileTitle` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca tytuł pliku. 

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a> CFileFind::GetFileTitle

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać tytuł znalezionego pliku.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Wartość zwracana

Tytuł pliku.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetFileTitle` .

`GetFileTitle` jest jedną z trzech `CFileFind` funkcji Członkowskich, które zwracają część nazwy pliku. Na poniższej liście opisano trzy i różnice między nimi:

- [GetFileName](#getfilename) zwraca nazwę pliku, łącznie z rozszerzeniem. Na przykład, wywołanie `GetFileName` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca nazwę pliku *myfile.txt*.

- [GetFilePath](#getfilepath) zwraca całą ścieżkę do pliku. Na przykład wywołanie `GetFilePath` wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca ścieżkę pliku *c:\myhtml\myfile.txt*.

- `GetFileTitle` Zwraca nazwę pliku, z wyłączeniem rozszerzenia pliku. Na przykład, wywołanie `GetFileTitle` do wygenerowania komunikatu użytkownika dotyczącego pliku *c:\myhtml\myfile.txt* zwraca tytuł pliku. 

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a> CFileFind::GetFileURL

Wywołaj tę funkcję elementu członkowskiego, aby pobrać określony adres URL.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Wartość zwracana

Pełny adres URL.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetFileURL` .

`GetFileURL` jest podobna do funkcji składowej [GetFilePath](#getfilepath), z tą różnicą, że zwraca adres URL w formularzu `file://path` . Na przykład, wywołanie `GetFileURL` w celu uzyskania pełnego adresu URL dla *myfile.txt* zwraca adres URL `file://c:\myhtml\myfile.txt` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a> CFileFind::GetLastAccessTime

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać godzinę ostatniego dostępu do określonego pliku.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parametry

*refTime*<br/>
Odwołanie do obiektu [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

*pTimeStamp*<br/>
Wskaźnik do struktury [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) zawierający czas ostatniego dostępu do pliku.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; 0, jeśli nie powiodło się. `GetLastAccessTime` Zwraca wartość 0 tylko wtedy, gdy [FindNextFile](#findnextfile) nigdy nie został wywołany dla tego `CFileFind` obiektu.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetLastAccessTime` .

> [!NOTE]
> Nie wszystkie systemy plików używają tej samej semantyki do implementowania sygnatury czasowej zwracanej przez tę funkcję. Ta funkcja może zwracać tę samą wartość zwracaną przez inne funkcje sygnatur czasowych, jeśli podstawowy system plików lub serwer nie obsługuje zachowywania atrybutu czasu. Zapoznaj się ze strukturą [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , aby uzyskać informacje na temat formatów czasu. W niektórych systemach operacyjnych zwrócony czas jest w strefie czasowej lokalnej dla komputera, w którym znajduje się plik. Aby uzyskać więcej informacji, zobacz Interfejs API Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a> CFileFind::GetLastWriteTime

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać ostatni czas zmiany pliku.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametry

*pTimeStamp*<br/>
Wskaźnik do struktury [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) zawierającej godzinę ostatniego zapisania pliku.

*refTime*<br/>
Odwołanie do obiektu [CTime](../../atl-mfc-shared/reference/ctime-class.md) .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; 0, jeśli nie powiodło się. `GetLastWriteTime` Zwraca wartość 0 tylko wtedy, gdy [FindNextFile](#findnextfile) nigdy nie został wywołany dla tego `CFileFind` obiektu.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetLastWriteTime` .

> [!NOTE]
> Nie wszystkie systemy plików używają tej samej semantyki do implementowania sygnatury czasowej zwracanej przez tę funkcję. Ta funkcja może zwracać tę samą wartość zwracaną przez inne funkcje sygnatur czasowych, jeśli podstawowy system plików lub serwer nie obsługuje zachowywania atrybutu czasu. Zapoznaj się ze strukturą [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , aby uzyskać informacje na temat formatów czasu. W niektórych systemach operacyjnych zwrócony czas jest w strefie czasowej lokalnej dla komputera, w którym znajduje się plik. Aby uzyskać więcej informacji, zobacz Interfejs API Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindgetlength"></a><a name="getlength"></a> CFileFind:: GetLength

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać długość znalezionego pliku w bajtach.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Wartość zwracana

Długość znalezionego pliku w bajtach.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetLength` .

`GetLength` używa struktury Win32 [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , aby uzyskać i zwrócić wartość rozmiaru pliku w bajtach.

> [!NOTE]
> Począwszy od MFC 7,0, `GetLength` obsługuje 64-bitowe liczby całkowite. Wcześniej istniejący kod utworzony przy użyciu tej nowszej wersji biblioteki może spowodować ostrzeżenia obcinania.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a> CFileFind:: GetRoot

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać katalog główny znalezionego pliku.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Wartość zwracana

Katalog główny aktywnego wyszukiwania.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `GetRoot` .

Ta funkcja członkowska zwraca specyfikator dysku i nazwę ścieżki służącą do uruchamiania wyszukiwania. Na przykład wywoływanie [FindFile —](#findfile) z `*.dat` wynikami `GetRoot` zwraca pusty ciąg. Przekazywanie ścieżki, `c:\windows\system\*.dll` na przykład, do `FindFile` `GetRoot` zwracanych wyników `c:\windows\system\` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetFileName](#getfilename).

## <a name="cfilefindisarchived"></a><a name="isarchived"></a> CFileFind:: IsArchived

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest archiwizowany.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Aplikacje oznaczają plik archiwum, którego kopia zapasowa ma zostać utworzona lub usunięta, przy użyciu FILE_ATTRIBUTE_ARCHIVE atrybutu pliku identyfikowanego w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) .

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsArchived` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a> CFileFind:: issprężony

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest skompresowany.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Skompresowany plik jest oznaczony FILE_ATTRIBUTE_COMPRESSED, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . W przypadku pliku ten atrybut wskazuje, że wszystkie dane w pliku są skompresowane. W przypadku katalogu ten atrybut wskazuje, że kompresja jest wartością domyślną dla nowo utworzonych plików i podkatalogów.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsCompressed` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a> CFileFind:: IsDirectory

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest katalogiem.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Plik, który jest katalogiem, jest oznaczony FILE_ATTRIBUTE_DIRECTORY atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) .

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsDirectory` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

Ten mały program odnosi się do każdego katalogu w C:\ dysk i drukuje nazwę katalogu.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a> CFileFind:: iskropek

Wywołaj tę funkcję elementu członkowskiego, aby przetestować dla bieżącego katalogu i znaczniki katalogu nadrzędnego podczas iterowania przez pliki.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli znaleziony plik ma nazwę "." lub "..", co oznacza, że znaleziony plik jest w rzeczywistości katalogiem. W przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsDots` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: IsDirectory](#isdirectory).

## <a name="cfilefindishidden"></a><a name="ishidden"></a> CFileFind:: IsHidden

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest ukryty.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Pliki ukryte, które są oznaczone FILE_ATTRIBUTE_HIDDEN, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . Plik ukryty nie jest uwzględniony w zwykłej liście katalogów.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsHidden` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindisnormal"></a><a name="isnormal"></a> CFileFind:: isnormal

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest zwykłym plikiem.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Pliki oznaczone FILE_ATTRIBUTE_NORMAL, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . Normalny plik nie ma ustawionych atrybutów. Wszystkie inne atrybuty pliku przesłaniają ten atrybut.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsNormal` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a> CFileFind:: IsReadOnly

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest tylko do odczytu.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Plik tylko do odczytu jest oznaczony FILE_ATTRIBUTE_READONLY, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . Aplikacje mogą odczytywać takie pliki, ale nie mogą ich zapisywać ani usuwać.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsReadOnly` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindissystem"></a><a name="issystem"></a> CFileFind:: IsSystem

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest plikiem systemowym.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Plik systemowy jest oznaczony FILE_ATTRIBUTE_SYSTEM, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . Plik systemowy jest częścią lub jest używany wyłącznie przez system operacyjny.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsSystem` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindistemporary"></a><a name="istemporary"></a> CFileFind:: IsTemporary

Wywołaj tę funkcję elementu członkowskiego, aby określić, czy znaleziony plik jest plikiem tymczasowym.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Plik tymczasowy jest oznaczony FILE_ATTRIBUTE_TEMPORARY, atrybut pliku identyfikowany w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) . Plik tymczasowy jest używany na potrzeby magazynu tymczasowego. Aplikacje powinny zapisywać do pliku tylko wtedy, gdy jest to absolutnie konieczne. Większość danych pliku pozostaje w pamięci bez opróżniania na nośnik, ponieważ plik zostanie wkrótce usunięty.

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `IsTemporary` .

Zobacz funkcja członkowska [MatchesMask](#matchesmask) , aby uzyskać pełną listę atrybutów plików.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CFileFind:: GetLength](#getlength).

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a> CFileFind:: m_pTM

Wskaźnik do `CAtlTransactionManager` obiektu.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Uwagi

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a> CFileFind::MatchesMask

Wywołaj tę funkcję elementu członkowskiego, aby przetestować atrybuty pliku w znalezionym pliku.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parametry

*dwMask*<br/>
Określa co najmniej jeden atrybut pliku określony w strukturze [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) w przypadku znalezionego pliku. Aby wyszukać wiele atrybutów, użyj operatora bitowego lub (&#124;). Dopuszczalna jest dowolna kombinacja następujących atrybutów:

- FILE_ATTRIBUTE_ARCHIVE plik jest plikiem archiwum. Aplikacje używają tego atrybutu do oznaczania plików do utworzenia kopii zapasowej lub usunięcia.

- FILE_ATTRIBUTE_COMPRESSED plik lub katalog jest skompresowany. W przypadku pliku oznacza to, że wszystkie dane w pliku są skompresowane. W przypadku katalogu oznacza to, że kompresja jest wartością domyślną dla nowo utworzonych plików i podkatalogów.

- FILE_ATTRIBUTE_DIRECTORY plik jest katalogiem.

- FILE_ATTRIBUTE_NORMAL plik nie ma ustawionych atrybutów. Ten atrybut jest prawidłowy tylko wtedy, gdy jest używany samodzielnie. Wszystkie inne atrybuty pliku przesłaniają ten atrybut.

- FILE_ATTRIBUTE_HIDDEN plik jest ukryty. Nie jest on uwzględniony w zwykłej liście katalogów.

- FILE_ATTRIBUTE_READONLY plik jest tylko do odczytu. Aplikacje mogą odczytywać pliki, ale nie mogą ich zapisywać ani usuwać.

- FILE_ATTRIBUTE_SYSTEM plik jest częścią lub jest używany wyłącznie przez system operacyjny.

- FILE_ATTRIBUTE_TEMPORARY plik jest używany na potrzeby magazynu tymczasowego. Aplikacje powinny zapisywać do pliku tylko wtedy, gdy jest to absolutnie konieczne. Większość danych pliku pozostaje w pamięci bez opróżniania na nośnik, ponieważ plik zostanie wkrótce usunięty.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0. Aby uzyskać rozszerzone informacje o błędzie, wywołaj [wartość GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)funkcji Win32.

### <a name="remarks"></a>Uwagi

Musisz wywołać [FindNextFile](#findnextfile) co najmniej raz przed wywołaniem metody `MatchesMask` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Zobacz także

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)<br/>
[Klasa CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Klasa CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Klasa CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Klasa CHttpFile](../../mfc/reference/chttpfile-class.md)
