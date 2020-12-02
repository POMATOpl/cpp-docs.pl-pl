---
title: 'TN033: wersja DLL biblioteki MFC'
description: Pokazuje, w jaki sposób używać bibliotek DLL udostępnionych przez MFC z aplikacjami MFC i biblioteką MFC.
ms.date: 11/30/2020
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.openlocfilehash: b9330fe7c756f962a8b06a04b840bfda343f3a49
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440317"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: wersja DLL biblioteki MFC

W tej uwadze opisano, jak można użyć programu *`MFCxx.DLL`* i *`MFCxxD.DLL`* (gdzie *XX* jest numerem wersji MFC) udostępnionych bibliotek dołączanych dynamicznie z aplikacjami MFC i bibliotekami DLL rozszerzenia MFC. Aby uzyskać więcej informacji na temat zwykłych bibliotek MFC DLL, zobacz [Używanie MFC jako części biblioteki DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

Ta Uwaga techniczna dotyczy trzech aspektów bibliotek DLL. Ostatnie dwa są przeznaczone dla bardziej zaawansowanych użytkowników:

- [Jak utworzyć bibliotekę DLL rozszerzenia MFC](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [Jak skompilować aplikację MFC, która korzysta z biblioteki DLL w wersji MFC](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [Jak są implementowane udostępnione biblioteki DLL MFC](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Jeśli interesuje Cię Kompilowanie biblioteki DLL przy użyciu biblioteki MFC, która może być używana z aplikacjami innymi niż MFC (znana jako *zwykła Biblioteka MFC DLL*), zobacz [Uwagi techniczne 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>Omówienie obsługi MFCxx.DLL: Terminologia i pliki

**Zwykła Biblioteka DLL MFC**: używasz zwykłej biblioteki MFC DLL do tworzenia autonomicznej biblioteki DLL przy użyciu niektórych klas MFC. Interfejsy w ramach granicy App/DLL są interfejsami "C", a aplikacja kliencka nie musi być aplikacją MFC.

Regularne biblioteki DLL MFC są wersjami bibliotek DLL obsługiwanych w MFC 1,0. Są one opisane w [uwadze technicznej 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) i przykładowej zaawansowanej koncepcji MFC [`DLLScreenCap`](../overview/visual-cpp-samples.md) .

> [!NOTE]
> Począwszy od Visual C++ w wersji 4,0, termin **USRDLL** jest przestarzały i został zastąpiony przez ZWYKŁĄ bibliotekę MFC DLL, która statycznie łączy się z MFC. Możesz również utworzyć zwykłą bibliotekę MFC DLL, która łączy dynamicznie z MFC.

MFC 3,0 (i nowsze) obsługuje regularne biblioteki MFC DLL ze wszystkimi nowymi funkcjami, takimi jak klasy OLE i bazy danych.

**AFXDLL**: określana również jako udostępniona wersja bibliotek MFC. Jest to nowa obsługa bibliotek DLL dodana w MFC 2,0. Sama Biblioteka MFC znajduje się w szeregu bibliotek DLL (opisanych poniżej). Aplikacja kliencka lub biblioteka DLL dynamicznie łączy biblioteki DLL, których to wymaga. Interfejsy w ramach granicy Application/DLL są interfejsami klas C++/MFC. Aplikacja kliencka musi być aplikacją MFC. Ta biblioteka DLL obsługuje wszystkie funkcje MFC 3,0 (wyjątek: kod UNICODE nie jest obsługiwany w przypadku klas baz danych).

> [!NOTE]
> Począwszy od Visual C++ w wersji 4,0, ten typ biblioteki DLL jest określany jako "Biblioteka DLL rozszerzenia".

Ta Uwaga będzie używana *`MFCxx.DLL`* do odwoływania się do całego zestawu MFC DLL, który obejmuje:

- Debuguj: *`MFCxxD.DLL`* (połączone) i *`MFCSxxD.LIB`* (statyczny).

- Wydanie: *`MFCxx.DLL`* (połączone) i *`MFCSxx.LIB`* (statyczny).

- Debugowanie Unicode: *`MFCxxUD.DLL`* (łącznie) i *`MFCSxxD.LIB`* (static).

- Wersja Unicode: *`MFCxxU.DLL`* (łącznie) i *`MFCSxxU.LIB`* (statyczna).

> [!NOTE]
> *`MFCSxx[U][D].LIB`* Biblioteki są używane w połączeniu z udostępnionymi bibliotekami DLL MFC. Biblioteki te zawierają kod, który musi być statycznie połączony z aplikacją lub biblioteką DLL.

Aplikacja łączy się z odpowiednimi bibliotekami importu:

- Rozpocząć *`MFCxxD.LIB`*

- Usuwanie *`MFCxx.LIB`*

- Debugowanie Unicode: *`MFCxxUD.LIB`*

- Wydanie Unicode: *`MFCxxU.LIB`*

*Biblioteka DLL rozszerzenia MFC* jest biblioteką DLL, która rozszerza *`MFCxx.DLL`* (lub inne udostępnione biblioteki MFC). Tutaj Architektura składników MFC jest uruchamiana w. Jeśli klasa jest użyteczna z klasy MFC lub kompiluje inny zestaw narzędzi do MFC, można umieścić go w bibliotece DLL. Biblioteka DLL używa programu *`MFCxx.DLL`* , podobnie jak ostateczna aplikacja kliencka. Biblioteka DLL rozszerzenia MFC zezwala na klasy liści wielokrotnego użytku, klasy bazowe wielokrotnego użytku i widok i klasy dokumentów.

## <a name="pros-and-cons"></a>Specjaliści i wady

Dlaczego należy używać udostępnionej wersji biblioteki MFC

- Użycie biblioteki udostępnionej może spowodować zmniejszenie liczby aplikacji. (Minimalna aplikacja, która używa większości biblioteki MFC, jest mniejsza niż 10 tys.).

- Udostępniona wersja MFC obsługuje biblioteki DLL rozszerzeń MFC i zwykłych bibliotek DLL MFC.

- Jest to szybsze Kompilowanie aplikacji, która używa udostępnionych bibliotek MFC niż statycznie połączonej aplikacji MFC. Dzieje się tak dlatego, że nie jest konieczne łączenie MFC. Jest to szczególnie prawdziwe w **`DEBUG`** kompilacjach, w których konsolidator musi skompaktować informacje debugowania. Gdy aplikacja jest połączona z biblioteką DLL, która zawiera już informacje o debugowaniu, nie ma więcej informacji debugowania do kompaktowania.

Dlaczego nie należy używać udostępnionej wersji biblioteki MFC:

- Wysyłka aplikacji korzystającej z biblioteki udostępnionej wymaga dostarczania *`MFCxx.DLL`* i innych bibliotek do programu. *`MFCxx.DLL`* Program umożliwia swobodny pakiet redystrybucyjny, taki jak wiele bibliotek DLL, ale w programie INSTALACYJNYm nadal trzeba zainstalować bibliotekę DLL. Ponadto trzeba będzie dostarczyć inne redystrybucyjne biblioteki używane zarówno przez program, jak i biblioteki DLL MFC.

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> Jak napisać bibliotekę DLL rozszerzenia MFC

Biblioteka DLL rozszerzenia MFC jest biblioteką DLL, która zawiera klasy i funkcje rozszerzające funkcjonalność klas MFC. Biblioteka DLL rozszerzenia MFC używa udostępnionych bibliotek DLL MFC w taki sam sposób, w jaki są używane przez aplikację, z kilkoma dodatkowymi zagadnieniami:

- Proces kompilacji jest podobny do kompilowania aplikacji, która korzysta z udostępnionych bibliotek MFC z kilkoma dodatkowymi opcjami kompilatora i konsolidatora.

- Biblioteka DLL rozszerzenia MFC nie zawiera `CWinApp` klasy pochodnej.

- Biblioteka DLL rozszerzenia MFC musi udostępniać specjalne `DllMain` . AppWizard dostarcza `DllMain` funkcję, którą można modyfikować.

- Biblioteka DLL rozszerzenia MFC zwykle zapewnia procedurę inicjowania `CDynLinkLibrary` , jeśli biblioteka DLL rozszerzenia MFC eksportuje `CRuntimeClass` typy lub zasoby do aplikacji. Klasa pochodna `CDynLinkLibrary` może być używana, jeśli dane poszczególnych aplikacji muszą być obsługiwane przez bibliotekę DLL rozszerzenia MFC.

Te zagadnienia opisano szczegółowo poniżej. Zapoznaj się również z przykładem zaawansowane pojęcia MFC [`DLLHUSK`](../overview/visual-cpp-samples.md) . Przedstawiono w nim sposób:

- Kompilowanie aplikacji przy użyciu bibliotek udostępnionych. ( *`DLLHUSK.EXE`* jest aplikacją MFC, która łączy dynamicznie z bibliotekami MFC i innymi bibliotekami DLL).

- Kompiluj bibliotekę DLL rozszerzenia MFC. (Pokazuje, jak specjalne flagi, takie jak GET, są `_AFXEXT` używane podczas kompilowania biblioteki DLL rozszerzenia MFC).

- Kompiluj dwa przykłady bibliotek DLL rozszerzeń MFC. Jeden wskazuje podstawową strukturę biblioteki DLL rozszerzenia MFC z ograniczonymi eksportami (TESTDLL1), a drugi pokazuje eksportowanie całego interfejsu klasy (TESTDLL2).

Zarówno aplikacja kliencka, jak i wszystkie biblioteki DLL rozszerzenia MFC muszą używać tej samej wersji programu *`MFCxx.DLL`* . Postępuj zgodnie z konwencjami bibliotek DLL MFC i podaj wersję Debug i Release ( **`/release`** ) biblioteki DLL rozszerzenia MFC. Dzięki temu programy klienckie mogą kompilować zarówno wersje debugowania, jak i wydania aplikacji, a także połączyć je z odpowiednią wersją Debug lub wydanie wszystkich bibliotek DLL.

> [!NOTE]
> Ze względu na to, że nazwy C++ dekorowanie i Eksportuj, lista eksportu z biblioteki DLL rozszerzenia MFC może różnić się między wersjami Debug i wersjami tej samej biblioteki DLL i dll dla różnych platform. Wydanie *`MFCxx.DLL`* zawiera około 2000 punktów wejścia; debugowanie *`MFCxxD.DLL`* zawiera około 3000 wyeksportowane punkty wejścia.

### <a name="quick-note-on-memory-management"></a>Szybka Uwaga dotycząca zarządzania pamięcią

Sekcja zatytułowana "Zarządzanie pamięcią" w bliskiej części tej uwagi technicznej zawiera opis implementacji programu *`MFCxx.DLL`* przy użyciu współużytkowanej wersji biblioteki MFC. Informacje potrzebne do zaimplementowania pliku DLL rozszerzenia MFC zostały opisane tutaj.

*`MFCxx.DLL`* wszystkie biblioteki DLL rozszerzeń MFC ładowane do przestrzeni adresowej aplikacji klienckiej będą używać tego samego alokatora pamięci, ładowania zasobów i innych stanów MFC "Global", tak jakby znajdowały się w tej samej aplikacji. Jest to istotne, ponieważ biblioteki DLL inne niż MFC i zwykłe biblioteki MFC, które statycznie łączą się z MFC, są dokładnie takie same: Każda biblioteka DLL przydzieli z własnej puli pamięci.

Jeśli biblioteka DLL rozszerzenia MFC przydzieli pamięć, pamięć może swobodnie Intermix z dowolnym innym obiektem przydzielonym przez aplikację. Ponadto, jeśli aplikacja korzystająca z udostępnionych bibliotek MFC ulegnie awarii, system operacyjny utrzymuje integralność wszystkich innych aplikacji MFC, które współużytkują bibliotekę DLL.

Podobnie inne "globalne" Stany MFC, takie jak bieżący plik wykonywalny do ładowania zasobów, są również udostępniane między aplikacją kliencką, wszystkie biblioteki DLL rozszerzenia MFC i *`MFCxx.DLL`* samym sobą.

### <a name="building-an-mfc-extension-dll"></a>Kompilowanie biblioteki DLL rozszerzenia MFC

Możesz użyć AppWizard, aby utworzyć projekt biblioteki DLL rozszerzenia MFC i automatycznie wygenerował odpowiednie ustawienia kompilatora i konsolidatora. Generuje również `DllMain` funkcję, którą można modyfikować.

Jeśli konwertujesz istniejący projekt na bibliotekę DLL rozszerzenia MFC, Rozpocznij od ustawień standardowych, które kompilują się przy użyciu udostępnionej wersji MFC. Następnie wprowadź następujące zmiany:

- Dodaj **`/D_AFXEXT`** do flag kompilatora. W oknie dialogowym właściwości projektu wybierz kategorię preprocesora **C/C++**  >  **Preprocessor** . Dodaj `_AFXEXT` do pola **Zdefiniuj makra** oddzielające poszczególne elementy średnikami.

- Usuń **`/Gy`** przełącznik kompilatora. W oknie dialogowym właściwości projektu wybierz kategorię generowanie **kodu C/C++**  >  **Code Generation** . Upewnij się, że właściwość **Enable Function-Level link** nie jest włączona. To ustawienie ułatwia eksportowanie klas, ponieważ konsolidator nie usuwa funkcji, do których nie istnieje odwołanie. Jeśli oryginalny projekt skompilowano zwykłą bibliotekę DLL MFC, która jest statycznie połączona z MFC, Zmień **`/MT`** **`/MTd`** opcję kompilatora (lub) na **`/MD`** (lub **`/MDd`** ).

- Utwórz bibliotekę eksportu z **`/DLL`** opcją do połączenia. Ta opcja jest ustawiana podczas tworzenia nowego obiektu docelowego i określania biblioteki Dynamic-Link Win32 jako typu docelowego.

### <a name="changing-your-header-files"></a>Zmiana plików nagłówkowych

Typowym celem biblioteki DLL rozszerzenia MFC jest eksportowanie niektórych typowych funkcji do co najmniej jednej aplikacji, która może korzystać z tej funkcji. Zasadniczo Biblioteka DLL eksportuje klasy i funkcje globalne do użytku przez aplikacje klienckie.

Aby upewnić się, że każda funkcja członkowska jest oznaczona do zaimportowania lub wyeksportowania stosownie do potrzeb, użyj specjalnych deklaracji `__declspec(dllexport)` i `__declspec(dllimport)` . Gdy aplikacje klienckie używają klas, powinny być deklarowane jako `__declspec(dllimport)` . Po skompilowaniu biblioteki DLL rozszerzenia MFC funkcje powinny być deklarowane jako `__declspec(dllexport)` . Wbudowana Biblioteka DLL musi również eksportować funkcje, dzięki czemu programy klienckie mogą być powiązane z nimi w czasie ładowania.

Aby wyeksportować całą klasę, użyj `AFX_EXT_CLASS` w definicji klasy. Struktura definiuje to makro jako `__declspec(dllexport)` , gdy `_AFXDLL` `_AFXEXT` jest zdefiniowane, ale definiuje go, `__declspec(dllimport)` gdy `_AFXEXT` nie jest zdefiniowany. `_AFXEXT` jest definiowana tylko podczas kompilowania biblioteki DLL rozszerzenia MFC. Przykład:

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>Nie eksportuje całej klasy

Czasami warto wyeksportować tylko jeden z niezbędnych członków klasy. Na przykład, Jeśli eksportujesz `CDialog` klasę pochodną, może być konieczne tylko wyeksportowanie konstruktora i `DoModal` wywołania. Te elementy członkowskie można eksportować za pomocą pliku DEF biblioteki DLL, ale można również użyć go `AFX_EXT_CLASS` w taki sam sposób, jak w przypadku poszczególnych członków potrzebnych do eksportowania.

Przykład:

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

Po wykonaniu tych czynności może wystąpić problem, ponieważ nie wszystkie elementy członkowskie klasy są eksportowane. Problem polega na tym, że makra MFC działają prawidłowo. Niektóre makra pomocnika MFC w rzeczywistości deklarują lub definiują elementy członkowskie danych. Biblioteka DLL musi również eksportować te składowe danych.

Na przykład makro DECLARE_DYNAMIC jest zdefiniowane w następujący sposób podczas kompilowania biblioteki DLL rozszerzenia MFC:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

Wiersz, który rozpoczyna `static AFX_DATA` deklaruje obiekt statyczny wewnątrz klasy. Aby poprawnie wyeksportować tę klasę i uzyskać dostęp do informacji o środowisku uruchomieniowym z programu Client EXE, należy wyeksportować ten obiekt statyczny. Ze względu na to, że obiekt statyczny jest zadeklarowany za pomocą modyfikatora `AFX_DATA` , wystarczy zdefiniować tylko `AFX_DATA` `__declspec(dllexport)` podczas kompilowania biblioteki DLL. Zdefiniuj ją jako `__declspec(dllimport)` podczas kompilowania pliku wykonywalnego klienta.

Jak wspomniano powyżej, `AFX_EXT_CLASS` jest już zdefiniowany w ten sposób. Wystarczy zmienić definicję tak `AFX_DATA` , aby była taka sama jak `AFX_EXT_CLASS` wokół definicji klasy.

Przykład:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

MFC zawsze używa `AFX_DATA` symbolu na elementach danych, który definiuje w swoich makrach, więc ta technika będzie działała dla wszystkich takich scenariuszy. Na przykład będzie działała DECLARE_MESSAGE_MAP.

> [!NOTE]
> W przypadku eksportowania całej klasy, a nie wybranych elementów członkowskich klasy, statyczne elementy członkowskie danych są automatycznie eksportowane.

Możesz użyć tej samej techniki, aby automatycznie wyeksportować `CArchive` operator wyodrębniania dla klas, które używają makr DECLARE_SERIAL i IMPLEMENT_SERIAL. Wyeksportuj operator archiwum, przeciągając deklaracje klas (znajdujące się w pliku nagłówkowym) przy użyciu następującego kodu:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>Ograniczenia _AFXEXT

Możesz użyć `_AFXEXT` symbolu przed procesorem dla bibliotek DLL rozszerzenia MFC, o ile nie masz wielu warstw bibliotek DLL rozszerzeń MFC. Jeśli masz biblioteki DLL rozszerzenia MFC, które wywołują lub pochodzą z klas we własnych bibliotekach DLL rozszerzenia MFC, które następnie pochodzą od klas MFC, należy użyć własnego symbolu preprocesora, aby uniknąć niejednoznaczności.

Problem polega na tym, że w systemie Win32 należy jawnie zadeklarować wszystkie dane jako `__declspec(dllexport)` do eksportowania z biblioteki DLL i `__declspec(dllimport)` zaimportować je z biblioteki DLL. Podczas definiowania `_AFXEXT` , nagłówki MFC upewnij się, że `AFX_EXT_CLASS` jest prawidłowo zdefiniowany.

Jeśli masz wiele warstw, jeden z nich `AFX_EXT_CLASS` jest niewystarczający: Biblioteka DLL rozszerzenia MFC może eksportować własne klasy, a także importować inne klasy z innej biblioteki DLL rozszerzenia MFC. Aby rozwiązać ten problem, należy użyć specjalnego symbolu preprocesora, który wskazuje, że tworzysz bibliotekę DLL, zamiast korzystać z biblioteki DLL. Załóżmy na przykład, że istnieją dwie biblioteki DLL rozszerzenia MFC, *`A.DLL`* i *`B.DLL`* . Każdy z nich eksportuje niektóre klasy w *`A.H`* i *`B.H`* , odpowiednio. *`B.DLL`* używa klas z *`A.DLL`* . Pliki nagłówkowe będą wyglądać następująco:

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

Gdy *`A.DLL`* jest tworzona, jest skompilowana przy użyciu **`/DA_IMPL`** i gdy *`B.DLL`* jest skompilowana, jest skompilowana przy użyciu **`/DB_IMPL`** . Przy użyciu oddzielnych symboli dla każdej biblioteki DLL `CExampleB` jest eksportowany i `CExampleA` importowany podczas kompilowania *`B.DLL`* . `CExampleA` jest eksportowany podczas kompilowania *`A.DLL`* i importowania, gdy jest używany przez *`B.DLL`* lub inny klient.

Tego typu warstw nie można wykonać podczas korzystania z `AFX_EXT_CLASS` symboli wbudowanych i `_AFXEXT` preprocesora. Opisana powyżej technika rozwiązuje ten problem w taki sam sposób, jak w przypadku MFC. MFC korzysta z tej techniki podczas kompilowania bibliotek DLL rozszerzeń MFC, baz danych i sieci.

### <a name="not-exporting-the-entire-class"></a>Nie eksportuje całej klasy

Po ponownym wyeksportowaniu całej klasy należy zachować szczególną ostrożność. Upewnij się, że niezbędne elementy danych utworzone przez makra MFC są poprawnie wyeksportowane. Można to zrobić przez ponowne zdefiniowanie `AFX_DATA` do określonego makra klasy. Zdefiniuj ją ponownie, gdy nie eksportujesz całej klasy.

Przykład:

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

Oto kod, który należy umieścić w głównym pliku źródłowym dla biblioteki DLL rozszerzenia MFC. Powinien on występować po standardowym uwzględnieniu. Gdy używasz AppWizard do tworzenia plików początkowych dla biblioteki DLL rozszerzenia MFC, dostarcza `DllMain` dla Ciebie.

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

Wywołanie do `AfxInitExtensionModule` przechwytywania klas środowiska uruchomieniowego modułu ( `CRuntimeClass` struktury) i jego fabryk obiektów ( `COleObjectFactory` obiektów) do użycia w przyszłości podczas `CDynLinkLibrary` tworzenia obiektu. Wywołanie (opcjonalne) `AfxTermExtensionModule` umożliwia MFC czyszczenie biblioteki DLL rozszerzenia MFC podczas każdego odłączenia procesu (co się dzieje po zakończeniu procesu lub gdy biblioteka DLL zostaje zwolniona przez `FreeLibrary` wywołanie) z biblioteki DLL rozszerzenia MFC. Ponieważ większość bibliotek DLL rozszerzeń MFC nie są ładowane dynamicznie (zwykle są one połączone za pośrednictwem ich bibliotek importu), wywołanie `AfxTermExtensionModule` zazwyczaj nie jest konieczne.

Jeśli aplikacja ładuje i zwalnia biblioteki DLL rozszerzenia MFC dynamicznie, należy wywołać `AfxTermExtensionModule` jak pokazano powyżej. Upewnij się również, że funkcja `AfxLoadLibrary` and `AfxFreeLibrary` (zamiast Functions `LoadLibrary` i `FreeLibrary` ) używa wielu wątków lub dynamicznie ładuje bibliotekę MFC DLL. Za pomocą `AfxLoadLibrary` i `AfxFreeLibrary` upewnij się, że kod uruchamiania i zamykania, który jest wykonywany, gdy biblioteka DLL rozszerzenia MFC jest załadowana i zwolniona, nie powoduje uszkodzenia globalnego stanu MFC.

Plik nagłówkowy *`AFXDLLX.H`* zawiera specjalne definicje struktur używanych w bibliotekach DLL rozszerzenia MFC, takich jak definicja dla `AFX_EXTENSION_MODULE` i `CDynLinkLibrary` .

Globalna *extensionDLL* musi być zadeklarowana jako pokazana. W przeciwieństwie do 16-bitowej wersji MFC, można przydzielić pamięć i wywoływać funkcje MFC w tym czasie, ponieważ *`MFCxx.DLL`* jest ona w pełni inicjowana przez czas `DllMain` wywoływany przez użytkownika.

### <a name="sharing-resources-and-classes"></a>Udostępnianie zasobów i klas

Proste biblioteki DLL rozszerzeń MFC potrzebują tylko wyeksportować kilka funkcji o niskiej przepustowości do aplikacji klienckiej i nic nie rób. Więcej bibliotek DLL intensywnie korzystających z interfejsu użytkownika może chcieć wyeksportować zasoby i klasy języka C++ do aplikacji klienckiej.

Eksportowanie zasobów odbywa się za pomocą listy zasobów. W każdej aplikacji jest pojedynczo dołączoną listą `CDynLinkLibrary` obiektów. Podczas wyszukiwania zasobu większość standardowych implementacji MFC, które ładują zasoby, najpierw sprawdzają się w bieżącym module zasobów ( `AfxGetResourceHandle` ) i jeśli nie została znaleziona, przeprowadzi listę `CDynLinkLibrary` obiektów próbujących załadować żądany zasób.

Dynamiczne tworzenie obiektów języka C++ z nazwą klasy języka C++ jest podobne. Mechanizm deserializacji obiektu MFC musi mieć wszystkie `CRuntimeClass` zarejestrowane obiekty, aby można je było odtworzyć przez dynamiczne utworzenie obiektu C++ dla wymaganego typu w oparciu o to, co zostało wcześniej zapisane.

Jeśli aplikacja kliencka ma używać klas w bibliotece DLL rozszerzenia MFC, które są `DECLARE_SERIAL` , należy wyeksportować klasy, aby były widoczne dla aplikacji klienckiej. Jest to również wykonywane przez przechodzenie do `CDynLinkLibrary` listy.

W przykładowej zaawansowanej koncepcji MFC [`DLLHUSK`](../overview/visual-cpp-samples.md) lista wygląda następująco:

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

*`MFCxx.DLL`* Wpis zazwyczaj znajduje się na końcu na liście zasobów i klas. *`MFCxx.DLL`* obejmuje wszystkie standardowe zasoby MFC, w tym ciągi monitów dla wszystkich identyfikatorów poleceń standardowych. Umieszczenie go na końcu listy umożliwia zarówno Bibliotekom DLL, jak i aplikacji klienckiej zaufać udostępnionym zasobom w programie *`MFCxx.DLL`* , zamiast mieć własne kopie.

Scalanie zasobów i nazw klas wszystkich bibliotek DLL w przestrzeni nazw aplikacji klienta ma wady, które należy zachować ostrożność podczas wybierania identyfikatorów lub nazw. Tę funkcję można wyłączyć, nie eksportując zasobów ani `CDynLinkLibrary` obiektów do aplikacji klienckiej. [`DLLHUSK`](../overview/visual-cpp-samples.md)Przykład służy do zarządzania współużytkowaną przestrzenią nazw zasobów przy użyciu wielu plików nagłówkowych. Zobacz [Uwagi techniczne 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) , aby uzyskać porady dotyczące korzystania z plików zasobów udostępnionych.

### <a name="initializing-the-dll"></a>Inicjowanie biblioteki DLL

Jak wspomniano powyżej, zazwyczaj warto utworzyć `CDynLinkLibrary` obiekt do eksportowania zasobów i klas do aplikacji klienckiej. Musisz podać wyeksportowany punkt wejścia, aby zainicjować bibliotekę DLL. Co więcej, jest to `void` procedura, która nie przyjmuje argumentów i zwraca wartość Nothing, ale może być dowolna.

Wszystkie aplikacje klienckie, które chcą korzystać z biblioteki DLL, muszą wywołać tę procedurę inicjowania, jeśli używasz tego podejścia. Możesz również przydzielić ten `CDynLinkLibrary` obiekt `DllMain` bezpośrednio po wywołaniu `AfxInitExtensionModule` .

Procedura inicjowania musi utworzyć `CDynLinkLibrary` obiekt w stercie bieżącej aplikacji, który jest połączony z informacjami o bibliotece DLL rozszerzenia MFC. Można to zrobić, definiując funkcję podobną do tej:

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

Nazwa procedury, *InitXxxDLL* w tym przykładzie, może być dowolna. Nie musi to być **`extern "C"`** , ale ułatwia zachowanie listy eksportu.

> [!NOTE]
> Jeśli biblioteka DLL rozszerzenia MFC jest używana ze zwykłej biblioteki MFC DLL, należy wyeksportować tę funkcję inicjującą. Ta funkcja musi zostać wywołana ze zwykłej biblioteki MFC DLL przed użyciem klas lub zasobów biblioteki DLL rozszerzenia MFC.

### <a name="exporting-entries"></a>Eksportowanie wpisów

Prostym sposobem eksportowania klas jest użycie `__declspec(dllimport)` i `__declspec(dllexport)` dla każdej klasy i funkcji globalnej, która ma zostać wyeksportowana. Jest to znacznie prostsze, ale jest mniej wydajne niż nazywanie każdego punktu wejścia w pliku DEF, jak opisano poniżej. Dzieje się tak dlatego, że masz mniej kontroli nad tym, jakie funkcje są eksportowane. Nie można eksportować funkcji według liczby porządkowej. TESTDLL1 i TESTDLL2 używają tej metody do eksportowania swoich wpisów.

Bardziej wydajna metoda polega na wyeksportowaniu poszczególnych wpisów, wprowadzając ich nazwę w pliku DEF. Ta metoda jest używana przez program *`MFCxx.DLL`* . Ponieważ eksportuje się selektywnie z naszej biblioteki DLL, musimy zdecydować, które konkretne interfejsy chcemy wyeksportować. Jest trudne, ponieważ należy określić nazwy zniekształcona dla konsolidatora w postaci wpisów w pliku DEF. Nie Eksportuj żadnej klasy języka C++, chyba że naprawdę potrzebujesz dla niej linku symbolicznego.

Jeśli wcześniej wyeksportowano klasy C++ z plikiem DEF, można utworzyć narzędzie do automatycznego wygenerowania tej listy. Można to zrobić za pomocą dwuetapowego procesu linku. Połącz bibliotekę DLL raz z brakiem eksportu i zezwól konsolidatorowi na wygenerowanie pliku mapy. Plik mapy zawiera listę funkcji, które mają zostać wyeksportowane. W przypadku niektórych ponownych rozmieszczenia można użyć go do wygenerowania wpisów eksportu dla pliku DEF. Lista eksportu *`MFCxx.DLL`* oraz biblioteki DLL rozszerzeń MFC OLE i Database, w których liczba tysięcy, została wygenerowana przy użyciu takiego procesu (choć nie jest to w pełni automatyczne i wymaga dostrojenia co jakiś czas).

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp a CDynLinkLibrary

Biblioteka DLL rozszerzenia MFC nie zawiera `CWinApp` obiektu pochodnego. Zamiast tego musi współpracować z `CWinApp` obiektem pochodnym aplikacji klienckiej. Oznacza to, że aplikacja kliencka jest właścicielem głównej pompy komunikatów, pętli bezczynności i tak dalej.

Jeśli biblioteka DLL rozszerzenia MFC musi obsługiwać dodatkowe dane dla każdej aplikacji, można utworzyć nową klasę z `CDynLinkLibrary` i tworzyć ją w `InitXxxDLL` procedurze opisane powyżej. Podczas uruchamiania Biblioteka DLL może sprawdzić listę obiektów bieżącej aplikacji, `CDynLinkLibrary` Aby znaleźć tę, dla której dana Biblioteka DLL rozszerzenia MFC.

### <a name="using-resources-in-your-dll-implementation"></a>Używanie zasobów w implementacji biblioteki DLL

Jak wspomniano powyżej, domyślne obciążenie zasobów przeprowadzi listę `CDynLinkLibrary` obiektów szukających pierwszego pliku exe lub dll, który ma żądany zasób. Wszystkie interfejsy API MFC i wszystkie kody wewnętrzne wykorzystują `AfxFindResourceHandle` listę zasobów w celu znalezienia dowolnego zasobu, niezależnie od miejsca, w którym się znajdują.

Jeśli chcesz ładować tylko zasoby z określonego miejsca, Użyj interfejsów API `AfxGetResourceHandle` i `AfxSetResourceHandle` Zapisz stary uchwyt i Ustaw nowe dojście. Należy pamiętać o przywróceniu starego uchwytu zasobów przed zwróceniem do aplikacji klienckiej. Przykładowa TESTDLL2 używa tego podejścia do jawnego ładowania menu.

Instruktażowanie listy ma pewne wady: jest nieco wolniejsze i wymaga zarządzania zakresami identyfikatorów zasobów. Ma ona zalety, aby aplikacja kliencka, która łączy się z kilkoma bibliotekami DLL rozszerzenia MFC, mogła używać dowolnego zasobu dostarczonego z biblioteką DLL bez konieczności określania dojścia do wystąpienia biblioteki DLL. `AfxFindResourceHandle` jest interfejsem API służącym do przechodzenia do listy zasobów w celu wyszukania danego dopasowania. Przyjmuje nazwę i typ zasobu, a następnie zwraca dojście do zasobu, w którym najpierw znajduje się zasób, lub wartość NULL.

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> Pisanie aplikacji korzystającej z wersji biblioteki DLL

### <a name="application-requirements"></a>Wymagania dotyczące aplikacji

Aplikacja, która używa udostępnionej wersji MFC, musi być zgodna z kilkoma podstawowymi regułami:

- Musi mieć `CWinApp` obiekt i przestrzegać standardowych reguł dla pompy komunikatów.

- Musi być skompilowany z zestawem wymaganych flag kompilatora (patrz poniżej).

- Musi on łączyć się z bibliotekami importu MFCxx. Ustawiając wymagane flagi kompilatora, nagłówki MFC są określane w czasie łącza, z którym biblioteka powinna łączyć się aplikacja.

- Aby uruchomić plik wykonywalny, *`MFCxx.DLL`* musi znajdować się na ścieżce lub w katalogu systemu Windows.

### <a name="building-with-the-development-environment"></a>Kompilowanie za pomocą środowiska programistycznego

Jeśli używasz wewnętrznego pliku reguł programu make z większością standardowych ustawień domyślnych, możesz łatwo zmienić projekt, aby skompilować wersję biblioteki DLL.

W poniższym kroku przyjęto założenie, że masz prawidłowo działającą aplikację MFC połączoną z programem *`NAFXCWD.LIB`* (na potrzeby debugowania) i *`NAFXCW.LIB`* (dla wydania) i chcesz ją przekonwertować na użycie udostępnionej wersji biblioteki MFC. Uruchamiasz środowisko programu Visual Studio i masz wewnętrzny plik projektu.

1. W menu **projekty** wybierz polecenie **Właściwości**. Na stronie **Ogólne** w obszarze **Ustawienia domyślne projektu** Ustaw Microsoft Foundation Classes na **Używanie MFC w współdzielonej bibliotece DLL** (MFCxx (d). dll).

### <a name="building-with-nmake"></a>Kompilowanie za pomocą NMAKE

Jeśli używasz funkcji zewnętrznego pliku reguł programu make kompilatora lub bezpośrednio korzystasz z programu NMAKE, musisz edytować swój plik reguł programu make, aby obsługiwał wymagane opcje kompilatora i konsolidatora.

Wymagane flagi kompilatora:

- **`/D_AFXDLL /MD`**
  **`/D_AFXDLL`**

Standardowe nagłówki MFC muszą `_AFXDLL` mieć symbol, który ma być zdefiniowany.

- **`/MD`** Aplikacja musi używać wersji biblioteki DLL biblioteki wykonawczej C.

Wszystkie inne flagi kompilatora stosują się do domyślnych ustawień MFC (na przykład `_DEBUG` dla debugowania).

Edytuj listę konsolidatora bibliotek. Zmień *`NAFXCWD.LIB`* na *`MFCxxD.LIB`* i Zmień *`NAFXCW.LIB`* na *`MFCxx.LIB`* . Zamień *`LIBC.LIB`* na *`MSVCRT.LIB`* . Podobnie jak w przypadku każdej innej biblioteki MFC, należy ją *`MFCxxD.LIB`* umieścić **przed** wszystkimi bibliotekami środowiska uruchomieniowego C.

Opcjonalnie Dodaj **`/D_AFXDLL`** do opcji kompilatora zasobów wydania i debugowania (ten, który faktycznie kompiluje zasoby w programie **`/R`** ). Ta opcja powoduje, że końcowy plik wykonywalny jest mniejszy przez udostępnienie zasobów znajdujących się w bibliotekach DLL MFC.

Po wprowadzeniu tych zmian wymagana jest pełna ponowna kompilacja.

### <a name="building-the-samples"></a>Kompilowanie przykładów

Większość przykładowych programów MFC można skompilować z Visual C++ lub z udostępnionego pliku reguł programu make zgodnego z NMAKE z wiersza polecenia.

Aby przekonwertować dowolny z tych przykładów *`MFCxx.DLL`* , można załadować plik MAK do Visual C++ i ustawić opcje projektu zgodnie z powyższym opisem. W przypadku korzystania z kompilacji NMAKE można określić `AFXDLL=1` w wierszu polecenia NMAKE, który będzie kompilować przykład przy użyciu udostępnionych BIBLIOTEK MFC.

Przykład [DLLHUSK](../overview/visual-cpp-samples.md) zaawansowanych koncepcji MFC jest kompilowany z biblioteką DLL MFC. Ten przykład nie tylko ilustruje sposób tworzenia aplikacji połączonej z programem *`MFCxx.DLL`* , ale również ilustruje inne funkcje pakietu DLL MFC, takie jak biblioteki DLL rozszerzenia MFC opisane w dalszej części tej uwagi technicznej.

### <a name="packaging-notes"></a>Informacje o pakowaniu

Wersje plików DLL ( *`MFCxx.DLL`* i *`MFCxxU.DLL`* ) są swobodnie redystrybucyjne. Wersje debugowania bibliotek DLL nie są swobodnie rozpowszechniane i powinny być używane tylko podczas opracowywania aplikacji.

Biblioteki DLL debugowania są udostępniane z informacjami o debugowaniu. Za pomocą debugera Visual C++ można śledzić wykonywanie zarówno aplikacji, jak i biblioteki DLL. Biblioteki DLL wydań ( *`MFCxx.DLL`* i *`MFCxxU.DLL`* ) nie zawierają informacji o debugowaniu.

W przypadku dostosowywania lub ponownego kompilowania bibliotek DLL, należy wywołać je coś innego niż "MFCxx". Plik SRC MFC *`MFCDLL.MAK`* zawiera opis opcji kompilacji i zawiera logikę zmiany nazwy biblioteki DLL. Zmiana nazwy plików jest konieczna, ponieważ te biblioteki DLL mogą być współużytkowane przez wiele aplikacji MFC. Jeśli niestandardowa wersja bibliotek DLL MFC zastąpią zainstalowane w systemie, można przerwać inną aplikację MFC przy użyciu udostępnionych bibliotek DLL MFC.

Ponowne kompilowanie bibliotek DLL MFC nie jest zalecane.

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> Sposób implementacji MFCxx.DLL

W poniższej sekcji opisano, w jaki sposób jest implementowana Biblioteka MFC DLL ( *`MFCxx.DLL`* i *`MFCxxD.DLL`* ). Informacje szczegółowe są również nieważne, jeśli wszystko, co chcesz zrobić, jest używane przez bibliotekę MFC DLL z aplikacją. Szczegóły w tym miejscu nie są niezbędne do poznania sposobu pisania biblioteki DLL rozszerzenia MFC, ale zrozumienie tej implementacji może pomóc w pisaniu własnej biblioteki DLL.

### <a name="implementation-overview"></a>Przegląd implementacji

Biblioteka MFC DLL jest naprawdę specjalnym przypadkiem biblioteki DLL rozszerzenia MFC, jak opisano powyżej. Ma dużą liczbę eksportów dla dużej liczby klas. Istnieje kilka dodatkowych czynności w bibliotece MFC DLL, które sprawiają, że jest ona jeszcze bardziej specjalna niż zwykła Biblioteka DLL rozszerzenia MFC.

### <a name="win32-does-most-of-the-work"></a>Win32 wykonuje większość pracy

16-bitowa wersja MFC wymagała szeregu specjalnych technik, w tym danych dla poszczególnych aplikacji w segmencie stosu, specjalnych segmentów utworzonych przez część kodu zestawu 80x86, kontekstów wyjątków dla procesów i innych technik. System Win32 bezpośrednio obsługuje dane poszczególnych procesów w bibliotece DLL, co jest potrzebne w większości czasu. Większość części *`MFCxx.DLL`* została *`NAFXCW.LIB`* spakowana w bibliotece DLL. Jeśli szukasz kodu źródłowego MFC, znajdziesz kilka `#ifdef _AFXDLL` przypadków, ponieważ nie ma żadnych specjalnych przypadków, które należy wykonać. Specjalne przypadki, w których istnieją szczególne problemy dotyczące środowiska Win32 w systemie Windows 3,1 (nazywanego również Win32s). Win32s nie obsługuje bezpośrednio poszczególnych procesów danych biblioteki DLL. Biblioteki MFC DLL muszą używać interfejsów API Win32 do uzyskiwania danych lokalnych.

### <a name="impact-on-library-sources-additional-files"></a>Wpływ na źródła biblioteki, dodatkowe pliki

Wpływ `_AFXDLL` wersji na normalne źródła biblioteki klas MFC i nagłówki jest stosunkowo drobny. Istnieje specjalny plik wersji ( *`AFXV_DLL.H`* ) i dodatkowy plik nagłówka ( *`AFXDLL_.H`* ) dołączony do głównego *`AFXWIN.H`* nagłówka. *`AFXDLL_.H`* Nagłówek zawiera `CDynLinkLibrary` klasę i inne szczegóły implementacji zarówno `_AFXDLL` aplikacji, jak i BIBLIOTEK DLL rozszerzeń MFC. *`AFXDLLX.H`* Nagłówek jest dostarczany do kompilowania bibliotek DLL rozszerzeń MFC (patrz powyżej, aby uzyskać szczegółowe informacje).

Regularne źródła do biblioteki MFC w bibliotece MFC SRC mają dodatkowy kod warunkowy pod `_AFXDLL` #ifdef. Dodatkowy plik źródłowy ( *`DLLINIT.CPP`* ) zawiera dodatkowy kod inicjalizacji biblioteki DLL i inne kleje dla udostępnionej wersji biblioteki MFC.

W celu skompilowania udostępnionej wersji MFC są udostępniane dodatkowe pliki. (Zobacz poniżej, aby uzyskać szczegółowe informacje na temat sposobu kompilowania biblioteki DLL).

- Dwa pliki DEF są używane do eksportowania punktów wejścia biblioteki MFC DLL dla wersji Debug ( *`MFCxxD.DEF`* ) i Release ( *`MFCxx.DEF`* ) biblioteki DLL.

- Plik RC ( *`MFCDLL.RC`* ) zawiera wszystkie standardowe zasoby MFC i `VERSIONINFO` zasób dla biblioteki DLL.

- Plik CLW ( *`MFCDLL.CLW`* ) umożliwia przeglądanie klas MFC przy użyciu ClassWizard. Ta funkcja nie jest określona w wersji biblioteki DLL MFC.

### <a name="memory-management"></a>Zarządzanie pamięcią

Aplikacja używająca *`MFCxx.DLL`* wspólnego alokatora pamięci zapewnianego przez *`MSVCRTxx.DLL`* , współużytkowana Biblioteka DLL środowiska uruchomieniowego C. Aplikacja, wszystkie biblioteki DLL rozszerzenia MFC, a także biblioteki MFC DLL używają tego alokatora pamięci współdzielonej. Za pomocą udostępnionego pliku DLL do alokacji pamięci biblioteki MFC mogą przydzielić pamięć, która jest później zwalniana przez aplikację lub odwrotnie. Ponieważ zarówno aplikacja, jak i Biblioteka DLL muszą korzystać z tego samego alokatora, nie należy przesłaniać globalnego języka C++ **`operator new`** ani **`operator delete`** . Te same reguły mają zastosowanie do pozostałej części procedur alokacji pamięci w czasie wykonywania C (takich jak,, `malloc` `realloc` `free` i innych).

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>Liczby porządkowe i klasy __declspec (dllexport) i nazwy bibliotek DLL

Nie używamy `class` **`__declspec(dllexport)`** funkcjonalności kompilatora języka C++. Zamiast tego lista eksportów jest dołączona do źródeł biblioteki klas ( *`MFCxx.DEF`* i *`MFCxxD.DEF`* ). Eksportowane jest tylko wybór zestawu punktów wejścia (funkcje i dane). Inne symbole, takie jak funkcje lub klasy prywatnej implementacji MFC, nie są eksportowane. Wszystkie eksporty są wykonywane według liczby porządkowej bez nazwy ciągu w tabeli nazw rezydentnych lub nierezydentnych.

Korzystanie z programu `class` **`__declspec(dllexport)`** może być efektywną alternatywą dla tworzenia mniejszych bibliotek DLL, ale w przypadku dużych bibliotek DLL, takich jak MFC, domyślny mechanizm eksportowania ma limity wydajności i pojemności.

Wszystko to oznacza, że firma Microsoft może spakować wiele funkcji w wersji *`MFCxx.DLL`* , która jest około 800 KB, bez wpływu na wydajność lub szybkość ładowania. *`MFCxx.DLL`* Ta technika nie została użyta w 100 KB. Technika umożliwia dodanie dodatkowych punktów wejścia na końcu pliku DEF. Umożliwia proste przechowywanie wersji bez wpływu na szybkość i wydajność eksportowania według liczby porządkowej. Wersje główne wersji biblioteki klas MFC zmienią nazwę biblioteki. Oznacza to, że *`MFC30.DLL`* jest to biblioteka DLL redystrybucyjna zawierająca wersję 3,0 biblioteki klas MFC. Uaktualnienie tej biblioteki DLL, powiedzmy, w hipotetycznej MFC 3,1, zamiast tego DLL byłoby nazwane *`MFC31.DLL`* . Ponownie, jeśli zmodyfikujesz kod źródłowy MFC w celu utworzenia niestandardowej wersji biblioteki MFC DLL, użyj innej nazwy (i najlepiej bez "MFC" w nazwie).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
