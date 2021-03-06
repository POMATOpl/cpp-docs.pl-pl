---
title: Edytuj i Refaktoryzacja kodu C++ w programie Visual Studio
description: Użyj edytora kodu C++ w programie Visual Studio do formatowania, nawigowania, zrozumienia i refaktoryzacji kodu.
ms.date: 05/31/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.topic: overview
ms.openlocfilehash: df59509f37567a6fe1d1e0cc6d5b9f38b953009c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924396"
---
# <a name="edit-and-refactor-c-code-in-visual-studio"></a>Edytuj i Refaktoryzacja kodu C++ w programie Visual Studio

Program Visual Studio udostępnia kilka narzędzi ułatwiających pisanie, edytowanie i refaktoryzację kodu.

## <a name="intellisense"></a>IntelliSense

IntelliSense to zaawansowane narzędzie do uzupełniania kodu, które sugeruje symbole i fragmenty kodu w trakcie pisania. Funkcja IntelliSense języka C++ w programie Visual Studio jest uruchamiana w czasie rzeczywistym, analizowanie bazy kodu podczas aktualizowania i udostępniania zaleceń. Gdy wpiszesz więcej znaków, lista zalecanych wyników zostanie zawężana.

![Lista rozwijana elementów członkowskich&#43;&#43; ](../ide/media/cpp-statement-completion.png)

Niektóre symbole są pomijane automatycznie, aby pomóc w zawężaniu wyników. Na przykład podczas uzyskiwania dostępu do elementów członkowskich obiektu klasy spoza klasy nie będzie można zobaczyć prywatnych członków domyślnie lub chronionych składowych (jeśli nie jesteś w kontekście klasy podrzędnej). Filtrowanie można dostosować za pomocą przycisków u dołu.

Po wybraniu symbolu z listy rozwijanej można uzupełnić go za pomocą **klawisza Tab** , **wprowadzić** lub jednego z innych znaków zatwierdzenia (domyślnie: `{ } [ ] ( ) . , : ; + - * / % & | ^ ! = ? @ # \` ). Aby dodać lub usunąć znaki z tej listy, wyszukaj ciąg "IntelliSense" w obszarze **Szybkie uruchamianie** (Ctrl + Q) i wybierz opcję **Edytor tekstu > C/C++ > Advanced** . Opcja **zatwierdzania list elementów członkowskich** umożliwia dostosowanie listy przy użyciu żądanych zmian.

Opcja **tryb filtrowania listy składowych** określa, jakie rodzaje sugestii autouzupełniania funkcji IntelliSense są widoczne. Domyślnie jest ustawiona wartość **rozmyte** . W przypadku wyszukiwania rozmytego, jeśli masz symbol o nazwie *MyAwesomeClass* , możesz wpisać "Mac" i znaleźć klasę w sugestiach autouzupełniania. Algorytm rozmyte ustawia minimalny próg, który musi spełniać symbole, aby były widoczne na liście. Filtrowanie **inteligentne** wyświetla wszystkie symbole zawierające podciągi, które pasują do wpisanych informacji. Filtrowanie **prefiksów** wyszukuje ciągi zaczynające się od wpisanego typu.

Aby uzyskać więcej informacji na temat funkcji IntelliSense języka C++, zobacz [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense) i [Konfigurowanie projektu C++ dla IntelliSense](/visualstudio/ide/visual-cpp-intellisense-configuration).

## <a name="intellicode"></a>IntelliCode

Rozszerzenia intellicode to funkcja IntelliSense z obsługą technologii AI. Najprawdopodobniej kandydujący znajduje się na górze listy uzupełniania. Zalecenia rozszerzenia intellicode są oparte na tysiącach projektów typu open source w usłudze GitHub z ponad 100 gwiazdkami. W połączeniu z kontekstem kodu, lista uzupełniania jest dostosowana do promowania typowych praktyk.

Podczas pisania języka C++ rozszerzenia intellicode będzie pomocne podczas korzystania z popularnych bibliotek, takich jak standardowa biblioteka języka C++. Kontekst kodu jest używany, aby najpierw dostarczyć najbardziej przydatne zalecenia. W poniższym przykładzie `size` funkcja członkowska jest często używana z `sort` funkcją, więc jest przedstawiona na górze listy wyników.

![C&#43;&#43; rozszerzenia intellicode](../ide/media/intellicode-cpp.png "C++ rozszerzenia intellicode")

::: moniker range="msvc-160"

W programie Visual Studio 2019 rozszerzenia intellicode jest dostępny jako składnik opcjonalny w obciążeniu **programowania aplikacji klasycznych w języku C++** . Aby upewnić się, że rozszerzenia intellicode jest aktywny dla języka C++, przejdź do pozycji **Narzędzia**  >  **Opcje**  >  **rozszerzenia intellicode**  >  **Ogólne** i ustaw **model C++ Base** na **włączone** .

::: moniker-end

::: moniker range="msvc-150"

W programie Visual Studio 2017 rozszerzenia intellicode jest dostępny jako rozszerzenie w Visual Studio Marketplace.

::: moniker-end

## <a name="predictive-intellisense-experimental"></a>Funkcja IntelliSense predykcyjna (eksperymentalna)

Funkcja **IntelliSense predykcyjna** jest eksperymentalną funkcją, która korzysta z rozpoznawania kontekstowego, aby ograniczyć liczbę wyników wyświetlanych na liście rozwijanej IntelliSense. Algorytm stosuje dopasowanie typu, aby wyświetlić tylko te wyniki, które pasują do oczekiwanego typu. W najprostszym przypadku, jeśli wpiszesz `int x =` i wywołajesz listę rozwijaną IntelliSense, zobaczysz tylko liczby całkowite lub funkcje zwracające liczby całkowite. Ta funkcja jest domyślnie wyłączona, ponieważ nadal trwa tworzenie. Najlepiej sprawdza się w przypadku symboli globalnych; funkcje składowe nie są jeszcze obsługiwane. Można ją włączyć, wpisując "predykcyjne" w **szybkim uruchomieniu** lub wybierając opcje **Narzędzia**  >  **Options**  >  **Edytor tekstu**  >  **C/C++**  >  **eksperymentalne**  >  **Włącz funkcję IntelliSense predykcyjną** .

Aby zastąpić **predykcyjną funkcję IntelliSense** i wyświetlić dłuższą listę, naciśnij **klawisze Ctrl + J** . Jeśli funkcja **IntelliSense predykcyjna** jest włączona, wywołanie **klawiszy Ctrl + J** spowoduje usunięcie filtra predykcyjnego. Naciśnięcie **klawiszy Ctrl + J** ponownie usuwa filtr dostępności z listy elementów członkowskich, tam gdzie ma to zastosowanie. Przycisk ([+]) pod listą rozwijaną IntelliSense ma taki sam efekt jak **Ctrl + J** . Umieść kursor nad przyciskiem, aby zobaczyć informacje o tym, co jest wyświetlane.

![Język C&#43;&#43; funkcji IntelliSense predykcyjnej](../ide/media/predictive-intellisense-cpp.png "Funkcja IntelliSense predykcyjna")

Poprzedni zrzut ekranu pokazuje kilka przycisków na liście rozwijanej. Umożliwiają one filtry IntelliSense dla różnych rodzajów wyników:

- Zmienne i stałe
- Funkcje
- Typy
- Makra
- Wyliczenia
- Przestrzenie nazw

Przycisk jest wyświetlany tylko wtedy, gdy jest on istotny dla bieżącej sesji IntelliSense. Zazwyczaj nie widzisz wszystkich przycisków w tym samym czasie.

## <a name="template-intellisense"></a>IntelliSense szablonu

Gdy karetka znajduje się wewnątrz definicji szablonu, pojawi się **pasek szablonu** , który umożliwia podanie przykładowych argumentów szablonu dla funkcji IntelliSense.

![Szablon języka C&#43;&#43; IntelliSense przedstawia istniejące wystąpienia](../ide/media/template-intellisense-cpp-1.png "Funkcja IntelliSense szablonów Wyświetla istniejące wystąpienia")

Kliknij **\<T>** ikonę, aby rozwinąć/zwinąć **pasek szablonu** . Kliknij ikonę ołówka lub dwukrotnie kliknij **pasek szablonu** , aby otworzyć okno **Edycja** .

![Funkcja IntelliSense szablonu&#43;&#43; języka C](../ide/media/template-intellisense-cpp-3.png "IntelliSense szablonu")

Zmiany wprowadzone w oknie są stosowane bezpośrednio do kodu źródłowego, dzięki czemu można zobaczyć efekty w czasie rzeczywistym.

Pasek szablonu może automatycznie wypełniać kandydatów w oparciu o wystąpienia w kodzie. Kliknij przycisk **Dodaj wszystkie istniejące wystąpienia** , aby wyświetlić listę wszystkich konkretnych argumentów, które zostały użyte do utworzenia wystąpienia szablonu w bazie kodu.

![Lista wyników IntelliSense szablonu&#43;&#43; języka C](../ide/media/template-intellisense-cpp-2.png "Lista wyników IntelliSense szablonu")

Okno w dolnej części edytora pokazuje, w jaki sposób znaleziono każde wystąpienie i jakie jego argumenty były.

![Mapa wystąpienia IntelliSense szablonu&#43;&#43; języka C](../ide/media/template-intellisense-cpp-4.png "Mapa tworzenia wystąpień IntelliSense szablonu")

Informacje **paska szablonu** są traktowane jako specyficzne dla użytkownika. Jest on przechowywany w folderze. vs i nie jest przekazany do kontroli źródła.

## <a name="error-squiggles-and-quick-fixes"></a>Zygzaki błędów i szybkie poprawki

Jeśli Edytor wykrywa problemy z kodem, spowoduje to dodanie kolorowych zygzaków w obszarze problemu. Czerwona zygzakowata oznacza kod, który nie kompiluje się. Zielone zygzaki wskazują inne rodzaje problemów, które nadal mogą być poważne. Możesz otworzyć okno **Lista błędów** , aby uzyskać więcej informacji o problemach.

W przypadku niektórych rodzajów błędów, a także wspólnych wzorców kodowania, Edytor będzie oferować **szybką poprawkę** w postaci żarówki, która pojawia się po umieszczeniu wskaźnika myszy na zygzaku. Kliknij strzałkę w dół, aby wyświetlić sugestie.

W poniższym przykładzie `vector` zadeklarowano, ale nie znaleziono definicji, dlatego edytor oferuje niezbędny plik nagłówka:

![Zrzut ekranu przedstawiający zygzaki błędów i szybką poprawkę zaoferowaną przez Edytor.](../ide/media/quick-fix-for-header-cpp.png "Szybka naprawa języka C++")

Edytor oferuje również szybkie poprawki w przypadku niektórych możliwości refaktoryzacji. Na przykład, Jeśli deklarujesz klasę w pliku nagłówkowym, Visual Studio będzie oferować definicję dla niego w osobnym pliku. cpp.

![Zrzut ekranu przedstawiający stronę szybkie rozwiązywanie przy użyciu opcji Utwórz definicję iteratora trasy kanału w obszarze kanały kropka C P p z wyróżnioną opcją.](../ide/media/quick-fix.png "Szybka naprawa języka C++")

## <a name="change-tracking"></a>Śledzenie zmian

Po każdym wprowadzeniu zmian w pliku żółty pasek jest wyświetlany po lewej stronie, aby wskazać, że wprowadzono niezapisane zmiany. Po zapisaniu pliku pasek zmieni kolor na zielony. Zielone i żółte słupki są zachowywane, o ile dokument jest otwarty w edytorze. Reprezentują one zmiany wprowadzone od czasu ostatniego otwarcia dokumentu.

![Śledzenie zmian&#43;&#43; C](../ide/media/change-tracking-cpp.png "Śledzenie zmian")

## <a name="move-code"></a>Przenieś kod

Linie kodu można przenieść w górę i w dół, zaznaczając je, przytrzymując klawisz Alt i naciskając klawisze strzałek w **górę/w dół** .

## <a name="insert-snippets"></a>Wstaw fragmenty kodu

Wstawka jest wstępnie zdefiniowanym fragmentem kodu źródłowego. Kliknij prawym przyciskiem myszy pojedynczy punkt lub w zaznaczonym tekście, aby wstawić fragment kodu lub otoczyć zaznaczony tekst fragmentem. Na poniższej ilustracji przedstawiono trzy kroki, aby umieścić wybraną instrukcję z pętlą for. Żółte wyróżnienia w końcowym obrazie są edytowalnymi polami dostępnymi za pomocą klawisza Tab. Aby uzyskać więcej informacji, zobacz [fragmenty kodu](/visualstudio/ide/code-snippets).

![&#43;&#43; Wstawianie fragmentu kodu w języku C&#45;w dół](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>Dodaj klasę

Dodaj nową klasę z menu **projekt** lub z menu kontekstowego w **Eksplorator rozwiązań** :

![Dodaj nową klasę w języku C&#43;&#43;](../ide/media/vs2017-add-class.png "vs2015_cpp_add_class")

Można również użyć kreatora klas do modyfikacji lub przeanalizowania istniejącej klasy.

![Kreator klasy języka C&#43;&#43; ](../ide/media/vs2017-class-wizard.png)

Aby uzyskać więcej informacji, zobacz [Dodawanie funkcji za pomocą kreatorów kodu (C++)](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="refactoring"></a>Refaktoryzacja

Refaktoryzacje są dostępne w menu kontekstowym szybkiej akcji lub przez kliknięcie [żarówki](/visualstudio/ide/perform-quick-actions-with-light-bulbs) w edytorze.  Niektóre znajdują się również w menu **edytuj > refaktoryzacji** .  Są one następujące:

- [Zmień nazwę](refactoring/rename.md)
- [Extract — Funkcja](refactoring/extract-function.md)
- [Implementuj czyste wirtualne](refactoring/implement-pure-virtuals.md)
- [Utwórz deklarację/definicję](refactoring/create-declaration-definition.md)
- [Przenieś definicję funkcji](refactoring/move-definition-location.md)
- [Konwertuj na literał nieprzetworzonego ciągu](refactoring/convert-to-raw-string-literal.md)
- [Zmień sygnaturę](refactoring/change-signature.md)

## <a name="code-style-enforcement-with-clangformat-and-editorconfig"></a>Wymuszanie stylu kodu z ClangFormat i EditorConfig

Program Visual Studio 2017 lub nowszy zawiera wbudowaną obsługę [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html), popularnego narzędzia do formatowania kodu dla języka C++ w oparciu o CLANG/LLVM. Wpisz "ClangFormat" w obszarze [szybkiego uruchamiania](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) , aby ustawić go tak, aby używał jednego z następujących popularnych formatów:

- LLVM
- Google
- Chrom
- Mozilla
- WebKit
- Visual Studio

Możesz również podać własny plik. Clang-format lub format _clang, aby zastosować niestandardowe reguły do wszystkich plików kodu na tym samym poziomie lub poniżej.

Pliki są łatwo udostępniane za pośrednictwem kontroli źródła, więc można wymusić konwencje kodowania dla całego zespołu deweloperów.

![Format języka C&#43;&#43; Clang](../ide/media/clang-format-cpp.png "Format Clang")

Program Visual Studio 2017 i jego nowsze wersje obsługują również [EditorConfig](https://editorconfig.org/), które działają w podobny sposób. ClangFormat jednak ma więcej opcji stylu niż EditorConfig, w tym reguł, które są specyficzne dla języka C++. Za pomocą **EditorConfig** można tworzyć pliki **EditorConfig** i umieszczać je w różnych folderach bazy kodu w celu określenia stylów kodu dla tych folderów i ich podfolderów. Plik **. editorconfig** zastępuje wszystkie inne pliki **. editorconfig** w folderach nadrzędnych i zastępuje wszelkie ustawienia formatowania skonfigurowane za pośrednictwem opcji **narzędzi**  >  **Options** . Możesz ustawić reguły dla kart zamiast spacji, wcięcia rozmiaru i inne. Aby uzyskać więcej informacji, zobacz [Tworzenie przenośnych ustawień edytora niestandardowego z EditorConfig](/visualstudio/ide/create-portable-custom-editor-options).

## <a name="other-formatting-options"></a>Inne opcje formatowania

Pole wyszukiwania **szybkiego uruchamiania** zapewnia najszybszy sposób znalezienia ustawienia lub narzędzia. Znajduje się ona w menu głównym. Po prostu zacznij pisać, a lista autouzupełniania przefiltruje wyniki.

![Szybkie uruchamianie programu Visual Studio](../ide/media/vs2015_cpp_quick_launch.png "Szybkie uruchamianie")

Aby ustawić opcje formatowania, takie jak wcięcia, uzupełnianie nawiasów klamrowych i kolorowanie, wpisz "formatowanie C++" w oknie **Szybkie uruchamianie** .

![Opcje formatowania języka C++](media/cpp-formatting-options.png)

Inne opcje formatowania można znaleźć w obszarze **Edytuj**  >  **Zaawansowane** w menu głównym.

![Opcje edycji zaawansowanej języka C++](media/edit-advanced-cpp.png)

Opcje włączania i konfigurowania funkcji edycji specyficznych dla języka C++ znajdują się w obszarze **Narzędzia**  >  **Opcje**  >  **Edytor tekstu**  >  **C/C++** . Po wybraniu opcji, która ma zostać ustawiona, możesz uzyskać więcej pomocy, naciskając klawisz **F1** , gdy okno dialogowe jest fokusem. Aby uzyskać ogólne opcje formatowania kodu, wpisz polecenie `Editor C++` **Szybkie uruchamianie** .

![Opcje > Visual Studio Tools](../ide/media/tools-options.png "Opcje edytora")

Funkcje eksperymentalne, które mogą lub nie mogą być uwzględnione w przyszłych wersjach programu Visual Studio, znajdują się w oknach dialogowych [edytora tekstu C++](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) . W programie Visual Studio 2017 i nowszych można włączyć funkcję **IntelliSense predykcyjną** w tym oknie dialogowym.

## <a name="see-also"></a>Zobacz też

[Czytanie i interpretacja kodu w języku C++](read-and-understand-code-cpp.md)</br>
[Nawigowanie po bazie kodu C++ w programie Visual Studio](navigate-code-cpp.md)</br>
[Współpraca z Live Shareami dla języka C++](live-share-cpp.md)
