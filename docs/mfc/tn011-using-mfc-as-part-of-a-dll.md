---
description: 'Dowiedz się więcej na temat: TN011: używanie MFC jako części biblioteki DLL'
title: 'TN011: używanie MFC jako części biblioteki DLL'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 11b50ce361fc9e41c48931daa6bffd30a8c9673e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216031"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: używanie MFC jako części biblioteki DLL

Ta Uwaga opisuje regularne biblioteki DLL MFC, które umożliwiają korzystanie z biblioteki MFC jako części biblioteki dołączanej dynamicznie (DLL) systemu Windows. Przyjęto założenie, że znasz biblioteki DLL systemu Windows i sposób ich kompilowania. Aby uzyskać informacje o bibliotekach DLL rozszerzenia MFC, za pomocą których można utworzyć rozszerzenia biblioteki MFC, zobacz [dll wersja biblioteki MFC](../mfc/tn033-dll-version-of-mfc.md).

## <a name="dll-interfaces"></a>Interfejsy DLL

regularne biblioteki DLL MFC zakładają interfejsy między aplikacją, a Biblioteka DLL jest określona w funkcjach, takich jak funkcje podobne do języka C lub jawnie wyeksportowane klasy. Nie można eksportować interfejsów klas MFC.

Jeśli zarówno Biblioteka DLL, jak i aplikacja chcą korzystać z MFC, obie opcje mogą korzystać z udostępnionej wersji bibliotek MFC lub statycznie łączyć się z kopią bibliotek. Aplikacja i Biblioteka DLL mogą korzystać z jednej z standardowych wersji biblioteki MFC.

regularne biblioteki MFC DLL mają kilka zalet:

- Aplikacja, która korzysta z biblioteki DLL, nie musi używać MFC i nie musi być aplikacją Visual C++.

- Przy użyciu zwykłych bibliotek DLL MFC, które statycznie łączą się z MFC, rozmiar biblioteki DLL zależy tylko od procedur środowiska uruchomieniowego MFC i C, które są używane i połączone.

- W przypadku zwykłych bibliotek DLL MFC, które dynamicznie łączą się z MFC, oszczędności w pamięci z używania udostępnionej wersji MFC mogą być znaczące. Należy jednak rozproszyć udostępnione biblioteki DLL, MFC \<*version*> . dll i Msvvcrt \<*version*> . dll, za pomocą biblioteki DLL.

- Projekt biblioteki DLL jest niezależny od sposobu implementacji klas. Projekt biblioteki DLL eksportuje tylko do żądanych interfejsów API. W związku z tym w przypadku zmiany implementacji regularne biblioteki DLL MFC są nadal ważne.

- Przy użyciu zwykłych bibliotek DLL MFC, które statycznie łączą się z MFC, jeśli zarówno Biblioteka DLL, jak i aplikacja używają MFC, nie ma żadnych problemów z aplikacją, która chce mieć inną wersję MFC niż biblioteka DLL lub odwrotnie. Ponieważ biblioteka MFC jest statycznie połączona z każdą biblioteką DLL lub EXE, nie ma pytania dotyczącej posiadanej wersji.

## <a name="api-limitations"></a>Ograniczenia interfejsu API

Niektóre funkcje MFC nie mają zastosowania do wersji biblioteki DLL, ze względu na ograniczenia techniczne lub, ponieważ te usługi są zwykle udostępniane przez aplikację. W przypadku bieżącej wersji MFC jedyną funkcją, która nie ma zastosowania, jest `CWinApp::SetDialogBkColor` .

## <a name="building-your-dll"></a>Kompilowanie biblioteki DLL

Podczas kompilowania zwykłych bibliotek DLL MFC, które statycznie łączą się z MFC, symbole `_USRDLL` i `_WINDLL` muszą być zdefiniowane. Kod biblioteki DLL musi być również skompilowany przy użyciu następujących przełączników kompilatora:

- **/D_WINDLL** oznacza kompilację dla biblioteki DLL

- **/D_USRDLL** określa, że tworzysz zwykła Biblioteka DLL MFC

Należy również zdefiniować te symbole i użyć tych przełączników kompilatora podczas kompilowania zwykłych bibliotek DLL MFC, które dynamicznie łączą się z MFC. Ponadto symbol `_AFXDLL` musi być zdefiniowany, a kod biblioteki DLL musi być skompilowany przy użyciu:

- **/D_AFXDLL** określa, że tworzysz ZWYKŁĄ bibliotekę MFC DLL, która łączy dynamicznie z MFC

Interfejsy (interfejsy API) między aplikacją a biblioteką DLL muszą zostać jawnie wyeksportowane. Zalecamy zdefiniowanie interfejsów jako niskich przepustowości i użycie tylko interfejsów języka C, jeśli jest to możliwe. Interfejsy Direct C są łatwiejsze w obsłudze niż bardziej złożone klasy języka C++.

Umieść swoje interfejsy API w osobnym nagłówku, który może być uwzględniony w plikach C i C++. Zapoznaj się z nagłówkiem zrzut ekranu przedstawiający. h w przykładowej zaawansowanej koncepcji MFC [DLLScreenCap](../overview/visual-cpp-samples.md) . Aby wyeksportować funkcje, wprowadź je w `EXPORTS` sekcji pliku definicji modułu (. DEF) lub Dołącz `__declspec(dllexport)` do definicji funkcji. Użyj, `__declspec(dllimport)` Aby zaimportować te funkcje do pliku wykonywalnego klienta.

Należy dodać makro AFX_MANAGE_STATE na początku wszystkich wyeksportowanych funkcji w zwykłych bibliotekach DLL MFC, które dynamicznie łączą się z MFC. To makro ustawia bieżący stan modułu dla biblioteki DLL. Aby użyć tego makra, Dodaj następujący wiersz kodu na początku funkcji wyeksportowanych z biblioteki DLL:

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain — > DllMain

Biblioteka MFC definiuje standardowy `DllMain` punkt wejścia środowiska Win32, który inicjuje obiekt pochodny [CWinApp](../mfc/reference/cwinapp-class.md) , jak w typowej aplikacji MFC. Umieść wszystkie inicjalizacje specyficzne dla biblioteki DLL w metodzie [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) , jak w typowej aplikacji MFC.

Należy zauważyć, że mechanizm [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run) nie ma zastosowania do biblioteki DLL, ponieważ aplikacja jest właścicielem głównej pompy komunikatów. Jeśli biblioteka DLL wyświetla Niemodalne okna dialogowe lub ma własne główne okno ramek, główna pompa komunikatów aplikacji musi wywoływać procedurę eksportu DLL, która wywołuje [CWinApp::P retranslatemessage](../mfc/reference/cwinapp-class.md#pretranslatemessage).

Zobacz przykład DLLScreenCap, aby użyć tej funkcji.

`DllMain`Funkcja, która zapewnia MFC, wywoła metodę [CWinApp:: ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) klasy, która pochodzi od `CWinApp` przed wyładowaniem biblioteki DLL.

## <a name="linking-your-dll"></a>Łączenie biblioteki DLL

Przy użyciu zwykłych bibliotek DLL MFC, które statycznie łączą się z MFC, należy połączyć bibliotekę DLL z NAFXCWD. lib lub NAFXCW. lib oraz z wersją środowiska uruchomieniowego języka C o nazwie libcmt. lib. Te biblioteki są wstępnie skompilowane i mogą być instalowane przez określenie ich podczas uruchamiania Instalatora Visual C++.

## <a name="sample-code"></a>Przykładowy kod

Zapoznaj się z przykładowym programem DLLScreenCap MFC Advanced koncepcji, aby uzyskać kompletny przykład. Kilka interesujących rzeczy, które należy zwrócić do tego przykładu, jest następująca:

- Flagi kompilatora biblioteki DLL i aplikacji są różne.

- Linie łączy i. Pliki DEF dla biblioteki DLL i dla aplikacji są różne.

- Aplikacja, która korzysta z biblioteki DLL, nie musi znajdować się w języku C++.

- Interfejs między aplikacją a biblioteką DLL to interfejs API, który jest użyteczny w języku C lub C++ i jest eksportowany z DLLScreenCap. def.

Poniższy przykład ilustruje interfejs API, który jest zdefiniowany w zwykłej bibliotece DLL MFC, która statycznie łączy się z MFC. W tym przykładzie deklaracja jest zawarta w `extern "C" { }` bloku dla użytkowników C++. Ma to kilka zalet. Po pierwsze sprawia, że interfejsy API biblioteki DLL mogą być używane przez aplikacje klienckie inne niż C + +. Po drugie zmniejsza to obciążenie związane z biblioteką DLL, ponieważ nazwa C++ dekorowanie nie zostanie zastosowana do wyeksportowanej nazwy. Wreszcie ułatwia to jawne dodanie do. Plik DEF (do eksportowania według liczby porządkowej) bez konieczności zajmowania się nazwą dekorowanie.

```cpp
#ifdef __cplusplus
extern "C" {
#endif  /* __cplusplus */

struct TracerData
{
    BOOL bEnabled;
    UINT flags;
};

BOOL PromptTraceFlags(TracerData FAR* lpData);

#ifdef __cplusplus
}
#endif
```

Struktury używane przez interfejs API nie pochodzą od klas MFC i są zdefiniowane w nagłówku interfejsu API. Zmniejsza to złożoność interfejsu między biblioteką DLL a aplikacją i sprawia, że biblioteka DLL jest użyteczna przez programy języka C.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
