---
title: Korzystanie z bibliotek DLL rozszerzeń MFC w bazie danych, OLE i Sockets w zwykłych bibliotekach DLL MFC
description: Pokazuje, w jaki sposób używać bibliotek DLL rozszerzenia bazy danych, OLE i Sockets MFC w zwykłych bibliotekach DLL MFC.
ms.date: 11/30/2020
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.openlocfilehash: a28e80c4d554a86f45f708e661382ee4a54eca9e
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440271"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Korzystanie z bibliotek DLL rozszerzeń MFC w bazie danych, OLE i Sockets w zwykłych bibliotekach DLL MFC

W przypadku korzystania z biblioteki MFC DLL z zwykłej biblioteki MFC DLL, jeśli biblioteka DLL rozszerzenia MFC nie jest podłączona do `CDynLinkLibrary` łańcucha obiektów zwykłej biblioteki MFC DLL, może wystąpić jeden lub więcej pokrewnych problemów. Ponieważ wersje debugowania baz danych MFC, OLE i Sockets obsługują biblioteki DLL rozszerzenia MFC, można zobaczyć podobne problemy, jeśli używasz tych funkcji MFC, nawet jeśli nie korzystasz jawnie z własnych bibliotek DLL rozszerzenia MFC. Niektóre objawy są następujące:

- Podczas próby deserializacji obiektu typu klasy zdefiniowanego w bibliotece DLL rozszerzenia MFC komunikat "Ostrzeżenie: nie można załadować CYourClass z archiwum. Nie zdefiniowano klasy ". pojawia się w oknie debugowanie śledzenia i nie można serializować obiektu.

- Może zostać zgłoszony wyjątek wskazujący na nieprawidłową klasę.

- Nie można załadować zasobów przechowywanych w bibliotece DLL rozszerzenia MFC, ponieważ `AfxFindResourceHandle` zwracane są `NULL` lub nieprawidłowe dojście do zasobów.

- `DllGetClassObject`, `DllCanUnloadNow` , i `UpdateRegistry` `Revoke` `RevokeAll` `RegisterAll` funkcje elementu członkowskiego `COleObjectFactory` nie mogą znaleźć fabryki klasy zdefiniowanej w bibliotece DLL rozszerzenia MFC.

- `AfxDoForAllClasses` nie działa dla żadnych klas w bibliotece DLL rozszerzenia MFC.

- Nie można załadować standardowej bazy danych MFC, gniazd lub zasobów OLE. Na przykład `AfxLoadString(AFX_IDP_SQL_CONNECT_FAIL)` zwraca pusty ciąg, nawet gdy zwykła Biblioteka MFC DLL jest prawidłowo używana z klasami baz danych MFC.

Rozwiązaniem tego problemu jest utworzenie i wyeksportowanie funkcji inicjalizacji w bibliotece DLL rozszerzenia MFC, która tworzy `CDynLinkLibrary` obiekt. Wywołaj tę funkcję inicjującą dokładnie raz z każdej zwykłej biblioteki MFC DLL, która używa biblioteki MFC DLL rozszerzenia.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>Obsługa MFC OLE, MFC Database (lub DAO) lub MFC Sockets

Jeśli korzystasz z obsługi biblioteki MFC OLE, MFC Database (lub DAO) lub MFC Sockets w zwykłej bibliotece MFC DLL, odpowiednio, biblioteki DLL rozszerzenia MFC debugowania MFC *`MFCOxxD.dll`* , *`MFCDxxD.dll`* i *`MFCNxxD.dll`* (gdzie *XX* jest numerem wersji) są połączone automatycznie. Wywołaj wstępnie zdefiniowaną funkcję inicjującą dla każdej z bibliotek DLL, których używasz:

- Aby zapewnić obsługę bazy danych, należy dodać wywołanie do `AfxDbInitModule` zwykłej biblioteki MFC DLL w `CWinApp::InitInstance` funkcji. Upewnij się, że to wywołanie występuje przed wywołaniem klasy bazowej lub dodanym kodem, który uzyskuje dostęp do *`MFCDxxD.dll`* . Ta funkcja nie przyjmuje parametrów i zwraca wartość `void` .

- W przypadku obsługi OLE należy dodać wywołanie do `AfxOleInitModule` zwykłej biblioteki DLL MFC, która jej `CWinApp::InitInstance` Funkcja. `COleControlModule::InitInstance`Funkcja wywołuje `AfxOleInitModule` już, więc jeśli tworzysz kontrolkę OLE i używasz `COleControlModule` , nie należy dodawać tego wywołania do `AfxOleInitModule` .

- W przypadku obsługi gniazd Dodaj wywołanie do `AfxNetInitModule` zwykłej biblioteki MFC DLL w `CWinApp::InitInstance` .

Kompilacje wydań bibliotek DLL i aplikacji MFC nie korzystają z oddzielnych bibliotek DLL dla obsługi baz danych, gniazd i OLE. Jednak jest bezpieczne wywoływanie tych funkcji inicjalizacji w trybie wydania.

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary — obiekty

Podczas każdej operacji wymienionej na początku tego artykułu MFC musi wyszukać określoną wartość lub obiekt. Na przykład podczas deserializacji MFC musi przeszukiwać wszystkie aktualnie dostępne klasy uruchomieniowe w celu dopasowania obiektów w archiwum przy użyciu ich właściwej klasy czasu wykonywania.

W ramach tych wyszukiwań MFC są skanowane za pomocą wszystkich bibliotek DLL rozszerzeń MFC używanych przez przeciągnięcie łańcucha `CDynLinkLibrary` obiektów. `CDynLinkLibrary` obiekty są automatycznie dołączane do łańcucha podczas ich konstruowania i są tworzone przez każdą bibliotekę DLL rozszerzenia MFC z kolei podczas inicjacji. Każdy moduł (aplikacja lub zwykła Biblioteka DLL MFC) ma swój własny łańcuch `CDynLinkLibrary` obiektów.

Aby można było połączyć bibliotekę DLL rozszerzenia MFC z `CDynLinkLibrary` łańcuchem, należy utworzyć `CDynLinkLibrary` obiekt w kontekście każdego modułu, który używa biblioteki MFC DLL rozszerzenia. Aby użyć biblioteki MFC DLL rozszerzenia w zwykłych bibliotekach DLL MFC, rozszerzenie DLL musi udostępniać wyeksportowaną funkcję inicjującą, która tworzy `CDynLinkLibrary` obiekt. Każda zwykła Biblioteka DLL MFC, która używa biblioteki DLL rozszerzenia MFC, musi wywoływać wyeksportowaną funkcję inicjującą.

Jeśli biblioteka DLL rozszerzenia MFC będzie używana tylko z poziomu aplikacji MFC i nigdy nie ze zwykłej biblioteki MFC DLL, wystarczy utworzyć `CDynLinkLibrary` obiekt w funkcji DLL rozszerzenia MFC `DllMain` . Jest to kod DLL rozszerzenia MFC DLL kreatora MFC. Podczas ładowania biblioteki DLL rozszerzenia MFC niejawnie, `DllMain` ładuje i wykonuje przed uruchomieniem aplikacji. Wszelkie operacje `CDynLinkLibrary` tworzenia są przewodne do domyślnego łańcucha, który Biblioteka MFC DLL rezerwuje dla aplikacji MFC.

Dobrym pomysłem jest posiadanie wielu `CDynLinkLibrary` obiektów z jednej biblioteki DLL rozszerzenia MFC w jednym łańcuchu. Jest to szczególnie prawdziwe, jeśli biblioteka DLL rozszerzenia MFC może zostać dynamicznie zwolniona z pamięci. Nie wywołuj funkcji inicjowania więcej niż raz z jednego modułu.

## <a name="sample-code"></a>Przykładowy kod

W tym przykładowym kodzie przyjęto założenie, że zwykła Biblioteka MFC DLL niejawnie łączy się z biblioteką DLL rozszerzenia MFC. Aby połączyć się niejawnie, Połącz z biblioteką importu (plik LIB) biblioteki DLL rozszerzenia MFC podczas tworzenia zwykłej biblioteki MFC DLL.

Następujące wiersze powinny znajdować się w źródle biblioteki DLL rozszerzenia MFC:

```cpp
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    if (dwReason == DLL_PROCESS_ATTACH)
    {
        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(extensionDLL, hInstance))
           return 0;
    }
    return 1;   // ok
}

// Exported DLL initialization is run in context of
// application or regular MFC DLL
extern "C" void WINAPI InitYourExtDLL()
{
    // create a new CDynLinkLibrary for this app
    new CDynLinkLibrary(extensionDLL);

    // add other initialization here
}
```

Należy pamiętać, aby wyeksportować funkcję **InitYourExtDLL** . Można użyć **`__declspec(dllexport)`** lub wyeksportować do pliku DEF dla biblioteki DLL, jak pokazano poniżej:

```def
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

Dodaj wywołanie do `InitInstance` elementu członkowskiego `CWinApp` obiektu pochodnego w każdej zwykłej bibliotece MFC DLL przy użyciu biblioteki DLL rozszerzenia MFC:

```cpp
// YourRegularDLL.cpp:

class CYourRegularDLL : public CWinApp
{
public:
    virtual BOOL InitInstance(); // Initialization
    virtual int ExitInstance();  // Termination

    // nothing special for the constructor
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }
};

BOOL CYourRegularDLL::InitInstance()
{
    // any DLL initialization goes here
    TRACE0("YOUR regular MFC DLL initializing\n");

    // wire any MFC extension DLLs into CDynLinkLibrary chain
    InitYourExtDLL();

    return TRUE;
}
```

### <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Inicjowanie biblioteki DLL rozszerzenia MFC](run-time-library-behavior.md#initializing-extension-dlls)

- [Inicjowanie zwykłych bibliotek DLL MFC](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Biblioteki DLL rozszerzeń MFC](extension-dlls.md)

- [Regularne biblioteki MFC DLL statycznie połączone z MFC](regular-dlls-statically-linked-to-mfc.md)

- [Regularne biblioteki DLL MFC połączone dynamicznie z MFC](regular-dlls-dynamically-linked-to-mfc.md)

- [Używanie MFC jako części biblioteki DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Wersja biblioteki DLL MFC](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>Zobacz też

[Biblioteki DLL rozszerzeń MFC](extension-dlls.md)
