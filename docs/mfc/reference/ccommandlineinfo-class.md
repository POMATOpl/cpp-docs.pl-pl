---
description: 'Dowiedz się więcej na temat: Klasa CCommandLineInfo'
title: Klasa CCommandLineInfo
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 4c26ae86608725caa61ad4d1077bed01a3f40385
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227926"
---
# <a name="ccommandlineinfo-class"></a>Klasa CCommandLineInfo

Pomoc w analizie wiersza polecenia podczas uruchamiania aplikacji.

## <a name="syntax"></a>Składnia

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Konstruuje `CCommandLineInfo` obiekt domyślny.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCommandLineInfo::P arseParam](#parseparam)|Zastąp to wywołanie zwrotne, aby przeanalizować poszczególne parametry.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCommandLineInfo:: m_bRunAutomated](#m_brunautomated)|Wskazuje, że `/Automation` znaleziono opcję wiersza polecenia.|
|[CCommandLineInfo:: m_bRunEmbedded](#m_brunembedded)|Wskazuje, że `/Embedding` znaleziono opcję wiersza polecenia.|
|[CCommandLineInfo:: m_bShowSplash](#m_bshowsplash)|Wskazuje, czy ekran powitalny powinien być pokazywany.|
|[CCommandLineInfo:: m_nShellCommand](#m_nshellcommand)|Wskazuje polecenie powłoki, które ma zostać przetworzone.|
|[CCommandLineInfo:: m_strDriverName](#m_strdrivername)|Wskazuje nazwę sterownika, jeśli polecenie powłoki jest drukowane na; w przeciwnym razie puste.|
|[CCommandLineInfo:: m_strFileName](#m_strfilename)|Wskazuje nazwę pliku do otwarcia lub wydrukowania; puste, jeśli polecenie powłoki jest nowe lub DDE.|
|[CCommandLineInfo:: m_strPortName](#m_strportname)|Wskazuje nazwę portu, jeśli polecenie powłoki jest drukowane na; w przeciwnym razie puste.|
|[CCommandLineInfo:: m_strPrinterName](#m_strprintername)|Określa nazwę drukarki, jeśli polecenie powłoki jest drukowane na; w przeciwnym razie puste.|
|[CCommandLineInfo:: m_strRestartIdentifier](#m_strrestartidentifier)|Wskazuje unikatowy identyfikator ponownego uruchomienia Menedżera ponownego uruchamiania, jeśli Menedżer ponownego uruchomienia ponownie uruchomił aplikację.|

## <a name="remarks"></a>Uwagi

Aplikacja MFC zazwyczaj tworzy lokalne wystąpienie tej klasy w funkcji [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) obiektu aplikacji. Ten obiekt jest następnie przesyłany do [CWinApp::P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline), który wielokrotnie wywołuje [ParseParam](#parseparam) w celu wypełnienia `CCommandLineInfo` obiektu. `CCommandLineInfo`Obiekt jest następnie przesyłany do [CWinApp::P rocessshellcommand](../../mfc/reference/cwinapp-class.md#processshellcommand) do obsługi argumentów wiersza polecenia i flag.

Można użyć tego obiektu do hermetyzacji następujących opcji i parametrów wiersza polecenia:

|Argument wiersza polecenia|Wykonano polecenie|
|----------------------------|----------------------|
|*aplikacje*|Nowy plik.|
|Nazwa pliku *aplikacji*|Otwórz plik.|
|*aplikacja* `/p` Nazwa pliku|Drukuj plik na drukarce domyślnej.|
|*aplikacja* `/pt` Nazwa pliku — port sterownika drukarki|Drukuj plik na określonej drukarce.|
|*aplikacja*`/dde`|Uruchom polecenie DDE i await.|
|*aplikacja*`/Automation`|Uruchom jako serwer automatyzacji OLE.|
|*aplikacja*`/Embedding`|Rozpocznij edycję osadzonego elementu OLE.|
|*aplikacja*`/Register`<br /><br /> *aplikacja*`/Regserver`|Informuje aplikację o wykonywaniu jakichkolwiek zadań rejestracji.|
|*aplikacja*`/Unregister`<br /><br /> *aplikacja*`/Unregserver`|Informuje aplikację o wykonywaniu jakichkolwiek zadań anulowania rejestracji.|

Utwórz nową klasę z `CCommandLineInfo` do obsługi innych flag i wartości parametrów. Przesłoń [ParseParam](#parseparam) , aby obsłużyć nowe flagi.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a> CCommandLineInfo::CCommandLineInfo

Ten konstruktor tworzy `CCommandLineInfo` obiekt z wartościami domyślnymi.

```
CCommandLineInfo();
```

### <a name="remarks"></a>Uwagi

Wartością domyślną jest wyświetlenie ekranu powitalnego ( `m_bShowSplash=TRUE` ) i wykonanie nowego polecenia w menu plik ( `m_nShellCommand` **= NewFile**).

Struktura aplikacji wywołuje [ParseParam](#parseparam) do wypełnienia elementów członkowskich danych tego obiektu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a> CCommandLineInfo:: m_bRunAutomated

Wskazuje, że `/Automation` flaga została znaleziona w wierszu polecenia.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Uwagi

W przypadku wartości TRUE oznacza to uruchomienie serwera automatyzacji OLE.

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a> CCommandLineInfo:: m_bRunEmbedded

Wskazuje, że `/Embedding` flaga została znaleziona w wierszu polecenia.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Uwagi

W przypadku wartości TRUE oznacza to rozpoczęcie edycji osadzonego elementu OLE.

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a> CCommandLineInfo:: m_bShowSplash

Wskazuje, że ekran powitalny powinien zostać wyświetlony.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Uwagi

W przypadku wartości TRUE oznacza to, że ekran powitalny tej aplikacji powinien być wyświetlany podczas uruchamiania. Domyślna implementacja [ParseParam](#parseparam) ustawia ten element członkowski danych na wartość true, jeśli [m_nShellCommand](#m_nshellcommand) jest równa `CCommandLineInfo::FileNew` .

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a> CCommandLineInfo:: m_nShellCommand

Wskazuje polecenie powłoki dla tego wystąpienia aplikacji.

```
m_nShellCommand;
```

### <a name="remarks"></a>Uwagi

Typ tego elementu członkowskiego danych to następujący typ wyliczeniowy, który jest zdefiniowany w `CCommandLineInfo` klasie.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

Aby uzyskać krótki opis tych wartości, zobacz poniższą listę.

- `CCommandLineInfo::FileNew` Wskazuje, że nie znaleziono nazwy pliku w wierszu polecenia.

- `CCommandLineInfo::FileOpen` Wskazuje, że nazwa pliku została znaleziona w wierszu polecenia i że w wierszu polecenia nie znaleziono żadnej z następujących flag: `/p` , `/pt` , `/dde` .

- `CCommandLineInfo::FilePrint` Wskazuje, że `/p` flaga została znaleziona w wierszu polecenia.

- `CCommandLineInfo::FilePrintTo` Wskazuje, że `/pt` flaga została znaleziona w wierszu polecenia.

- `CCommandLineInfo::FileDDE` Wskazuje, że `/dde` flaga została znaleziona w wierszu polecenia.

- `CCommandLineInfo::AppRegister` Wskazuje, że `/Register` `/Regserver` Flaga or została znaleziona w wierszu polecenia, a aplikacja została zaproszona o zarejestrowanie.

- `CCommandLineInfo::AppUnregister` Wskazuje, że `/Unregister` `/Unregserver` aplikacja lub żądanie wyrejestrowania.

- `CCommandLineInfo::RestartByRestartManager` Wskazuje, że aplikacja została uruchomiona ponownie przez Menedżera ponownego uruchamiania.

- `CCommandLineInfo::FileNothing` Wyłącza wyświetlanie nowego okna podrzędnego MDI przy uruchamianiu. Po zaprojektowaniu aplikacje MDI generowane przez Kreatora aplikacji wyświetlają nowe okno podrzędne podczas uruchamiania. Aby wyłączyć tę funkcję, aplikacja może użyć `CCommandLineInfo::FileNothing` jako polecenia powłoki, gdy wywołuje [elemencie ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand` jest wywoływana przez `InitInstance( )` wszystkie `CWinApp` klasy pochodne.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a> CCommandLineInfo:: m_strDriverName

Przechowuje wartość trzeciego parametru niebędącego flagą w wierszu polecenia.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Uwagi

Ten parametr jest zazwyczaj nazwą sterownika drukarki dla polecenia Print to Shell. Domyślna implementacja [ParseParam](#parseparam) ustawia ten element członkowski danych tylko wtedy, gdy `/pt` flaga została znaleziona w wierszu polecenia.

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a> CCommandLineInfo:: m_strFileName

Przechowuje wartość pierwszego parametru bez flagi w wierszu polecenia.

```
CString m_strFileName;
```

### <a name="remarks"></a>Uwagi

Ten parametr jest zwykle nazwą pliku do otwarcia.

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a> CCommandLineInfo:: m_strPortName

Przechowuje wartość czwartego parametru niebędącego flagą w wierszu polecenia.

```
CString m_strPortName;
```

### <a name="remarks"></a>Uwagi

Ten parametr jest zazwyczaj nazwą portu drukarki dla polecenia Print to Shell. Domyślna implementacja [ParseParam](#parseparam) ustawia ten element członkowski danych tylko wtedy, gdy `/pt` flaga została znaleziona w wierszu polecenia.

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a> CCommandLineInfo:: m_strPrinterName

Przechowuje wartość drugiego parametru niebędącego flagą w wierszu polecenia.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Uwagi

Ten parametr jest zazwyczaj nazwą drukarki do polecenia Print to Shell. Domyślna implementacja [ParseParam](#parseparam) ustawia ten element członkowski danych tylko wtedy, gdy `/pt` flaga została znaleziona w wierszu polecenia.

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a> CCommandLineInfo:: m_strRestartIdentifier

Unikatowy identyfikator ponownego uruchomienia w wierszu polecenia.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Uwagi

Identyfikator ponownego uruchomienia jest unikatowy dla każdego wystąpienia aplikacji.

Jeśli Menedżer ponownego uruchamiania opuszcza aplikację i jest skonfigurowany do jej ponownego uruchomienia, Menedżer ponownego uruchamiania wykonuje aplikację z wiersza polecenia z identyfikatorem ponownego uruchomienia jako parametr opcjonalny. Gdy Menedżer ponownego uruchamiania używa identyfikatora ponownego uruchomienia, aplikacja może ponownie otworzyć poprzednio otwarte dokumenty i odzyskać automatycznie zapisane pliki.

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a> CCommandLineInfo::P arseParam

Struktura wywołuje tę funkcję, aby analizować/interpretować poszczególne parametry z wiersza polecenia. Druga wersja różni się od pierwszego tylko w projektach Unicode.

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>Parametry

*pszParam*<br/>
Parametr lub flaga.

*bFlag*<br/>
Wskazuje, czy *pszParam* jest parametrem, czy flagą.

*Gaz*<br/>
Wskazuje, czy jest to ostatni parametr, czy flaga w wierszu polecenia.

### <a name="remarks"></a>Uwagi

[CWinApp::P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline) wywołuje `ParseParam` jeden raz dla każdego parametru lub flagi w wierszu polecenia, przekazując argument do *pszParam*. Jeśli pierwszym znakiem parametru jest " **-** " lub " **/** ", zostanie on usunięty i *bFlag* jest ustawiony na wartość true. Podczas analizowania końcowego parametru, wartość " *świetnie* " ma wartość true.

Domyślna implementacja tej funkcji rozpoznaje następujące flagi: `/p` , `/pt` ,, `/dde` `/Automation` i `/Embedding` , jak pokazano w poniższej tabeli:

|Argument wiersza polecenia|Wykonano polecenie|
|----------------------------|----------------------|
|*aplikacje*|Nowy plik.|
|Nazwa pliku *aplikacji*|Otwórz plik.|
|*aplikacja* `/p` Nazwa pliku|Drukuj plik na drukarce domyślnej.|
|*aplikacja* `/pt` Nazwa pliku — port sterownika drukarki|Drukuj plik na określonej drukarce.|
|*aplikacja*`/dde`|Uruchom polecenie DDE i await.|
|*aplikacja*`/Automation`|Uruchom jako serwer automatyzacji OLE.|
|*aplikacja*`/Embedding`|Rozpocznij edycję osadzonego elementu OLE.|
|*aplikacja*`/Register`<br /><br /> *aplikacja*`/Regserver`|Informuje aplikację o wykonywaniu jakichkolwiek zadań rejestracji.|
|*aplikacja*`/Unregister`<br /><br /> *aplikacja*`/Unregserver`|Informuje aplikację o wykonywaniu jakichkolwiek zadań anulowania rejestracji.|

Te informacje są przechowywane w [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded)i [m_nShellCommand](#m_nshellcommand). Flagi są oznaczone ukośnikiem " **/** " lub łącznikiem " **-** ".

Domyślna implementacja umieszcza pierwszy parametr bez flagi w [m_strFileName](#m_strfilename). W przypadku `/pt` flagi, domyślna implementacja przeniesie odpowiednio drugi, trzeci i czwarty nieflagowe parametry do [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername)i [m_strPortName](#m_strportname).

Domyślna implementacja ustawia również [m_bShowSplash](#m_bshowsplash) na true tylko w przypadku nowego pliku. W przypadku nowego pliku użytkownik podjął akcję obejmującą samą aplikację. W każdym innym przypadku, w tym otwierając istniejące pliki przy użyciu powłoki, akcja użytkownika obejmuje bezpośrednio ten plik. W przypadku punktu widzenia skoncentrowanego na dokumencie ekran powitalny nie musi ogłaszać uruchomienia aplikacji.

Przesłoń tę funkcję w klasie pochodnej, aby obsłużyć inne wartości flag i parametrów.

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::P rocessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
