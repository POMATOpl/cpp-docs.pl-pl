---
description: 'Dowiedz się więcej na temat: TN035: używanie wielu plików zasobów i plików nagłówkowych z Visual C++'
title: 'TN035: używanie wielu plików zasobów i plików nagłówków z programem Visual C++'
ms.date: 11/04/2016
f1_keywords:
- vc.resources
helpviewer_keywords:
- resource files, multiple
- TN035
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
ms.openlocfilehash: 347c816040d6e20cd9b7ee01f07662066981b8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215472"
---
# <a name="tn035-using-multiple-resource-files-and-header-files-with-visual-c"></a>TN035: używanie wielu plików zasobów i plików nagłówków z programem Visual C++

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje, jak edytor zasobów Visual C++ obsługuje wiele plików zasobów i plików nagłówkowych udostępnionych w pojedynczym projekcie lub udostępnianych w wielu projektach oraz jak można korzystać z tej pomocy. Ta uwaga odpowiada na następujące pytania:

- Kiedy warto podzielić projekt na wiele plików zasobów i/lub plików nagłówkowych oraz jak to zrobić

- Jak udostępnić wspólny nagłówek. Plik H między dwoma. RC — pliki

- Jak podzielić Zasoby projektu na wiele. RC — pliki

- Jak ty (i narzędzia) Zarządzaj zależnościami kompilacji między. RC,. CPP i. Pliki H

Należy pamiętać, że po dodaniu dodatkowego pliku zasobów do projektu ClassWizard nie rozpoznaje zasobów w dodanym pliku.

Ta uwaga ma na celu udzielenie odpowiedzi na powyższe pytania w następujący sposób:

- **Omówienie sposobu, w jaki Visual C++ zarządza plikami zasobów i plikami nagłówkowymi** , zawiera omówienie sposobu, w jaki zestaw zasobów zawiera polecenie w Visual C++ umożliwia używanie wielu plików zasobów i plików nagłówkowych w tym samym projekcie.

- **Analiza AppWizard — utworzona. RC i. H pliki** przeszukują wiele plików zasobów i nagłówków, które są używane przez aplikację utworzoną przez AppWizard. Te pliki służą jako dobry model dla dodatkowych plików zasobów i plików nagłówkowych, które można dodać do projektu.

- **Dołączenie dodatkowych plików nagłówkowych** opisuje, gdzie można uwzględnić wiele plików nagłówkowych i zawiera szczegółowe informacje, jak to zrobić.

- **Udostępnianie pliku nagłówka między dwoma. Pliki RC** pokazują, jak można udostępnić jeden plik nagłówkowy między wieloma. RC pliki w różnych projektach lub prawdopodobnie w tym samym projekcie.

- **Użycie wielu plików zasobów w tym samym projekcie** opisuje, gdzie można podzielić projekt na wiele. RC i zawiera szczegółowe informacje, jak to zrobić.

- **Wymuszanie nieedytowalnych plików Visual C++** opisuje, jak można upewnić się, że Visual C++ nie edytuje i przypadkowo ponownie sformatuj zasób niestandardowy.

- **Zarządzanie symbolami udostępnionymi przez wiele Visual C++ edytowane. Pliki RC** opisują sposób udostępniania tych samych symboli w wielu. RC i jak unikać przypisywania zduplikowanych wartości liczbowych ID.

- **Zarządzanie zależnościami między. RC,. CPP i. H** zawiera opis sposobu, w jaki Visual C++ Unikaj niepotrzebnego ponownego kompilowania. Pliki CPP, które są zależne od plików symboli zasobów.

- **Sposób, w jaki Visual C++ zarządzana, zawiera informacje** techniczne na temat tego, jak Visual C++ śledzi wiele (zagnieżdżone). Pliki RC i wiele plików nagłówkowych, które są #include pozostały przez. Plik RC.

## <a name="overview-of-how-visual-c-manages-resource-files-and-header-files"></a>Omówienie sposobu, w jaki Visual C++ zarządza plikami zasobów i plikami nagłówkowymi

Visual C++ zarządza pojedynczym. Plik zasobów RC i odpowiadający mu. H plik nagłówkowy jako ściśle sprzężoną parę plików. Podczas edytowania i zapisywania zasobów w programie. Plik RC, można pośrednio edytować i zapisywać symbole w odpowiednich. Plik H. Chociaż można otwierać i edytować wiele. RC pliki w danym momencie (przy użyciu interfejsu użytkownika MDI Visual C++) dla każdego z nich. Plik RC można pośrednio edytować dokładnie jeden odpowiedni plik nagłówkowy.

### <a name="symbol-header-file"></a>Plik nagłówka symboli

Domyślnie program Visual C++ zawsze nazywa odpowiedni zasób pliku nagłówkowego. H, niezależnie od nazwy pliku zasobów (np. MOJAAPL. RC). Za pomocą polecenia **zasób zawiera** z menu **Widok** w Visual C++ można zmienić nazwę tego pliku nagłówka, aktualizując plik nagłówka symboli w oknie dialogowym **zestaw zawiera** .

### <a name="read-only-symbol-directives"></a>Dyrektywy symboli Read-Only

Mimo że Visual C++ edytować tylko jeden plik nagłówkowy dla danego elementu. Plik RC, Visual C++ obsługuje odwołania do symboli zdefiniowanych w dodatkowych plikach nagłówkowych tylko do odczytu. Za pomocą polecenia **zasób zawiera** z menu **Widok** w Visual C++ można określić dowolną liczbę dodatkowych plików nagłówkowych tylko do odczytu jako dyrektywy symboli Read-Only. Ograniczenie "tylko do odczytu" oznacza, że po dodaniu nowego zasobu w. Plik RC, można użyć symbolu zdefiniowanego w pliku nagłówkowym tylko do odczytu; Jeśli jednak usuniesz zasób, symbol nadal pozostaje zdefiniowany w pliku nagłówkowym tylko do odczytu. Nie można zmienić wartości numerycznej przypisanej do symbolu tylko do odczytu.

### <a name="compile-time-directives"></a>Dyrektywy Compile-Time

Visual C++ obsługuje również zagnieżdżanie plików zasobów, z których jeden. Plik RC jest #include w innym. Podczas edytowania danego elementu. Plik RC przy użyciu Visual C++, wszystkie zasoby w #include pliki nie są widoczne. Ale podczas kompilowania. Plik RC, #include pliki. Za pomocą polecenia **zasób zawiera** z menu **Widok** w Visual C++ można określić dowolną liczbę #include. Pliki RC jako dyrektywy Compile-Time.

Zwróć uwagę na to, co się dzieje, jeśli przeczytasz do Visual C++. Plik RC, który #include inny. Plik RC, który *nie* jest określony jako dyrektywa Compile-Time. Ta sytuacja może wystąpić, gdy przejdziesz do Visual C++. Plik RC, który był wcześniej konserwowany ręcznie przy użyciu edytora tekstu. Gdy Visual C++ odczytuje #include. Plik RC Scala #include zasobów do elementu nadrzędnego. Plik RC. Po zapisaniu elementu nadrzędnego. Plik RC, Instrukcja #include, w efekcie, zostanie zastąpiony przez #include zasoby. Jeśli nie chcesz, aby scalanie było wykonywane, Usuń instrukcję #include z elementu nadrzędnego. Plik RC *przed* odczytaniem go do Visual C++; następnie za pomocą Visual C++ Dodaj tę samą instrukcję #include jako dyrektywę Compile-Time.

Visual C++ zapisuje w. Plik RC trzy rodzaje powyższego zestawu obejmują informacje (plik nagłówkowy symboli, dyrektywy symboli Read-Only i dyrektywy Compile-Time) w dyrektywach #include *i* w zasobach TEXTINCLUDE. Zasoby TEXTINCLUDE, szczegóły implementacji, które nie są zwykle potrzebne do obsłużenia, są wyjaśnione w [temacie jak Visual C++ zarządzanie zestaw zawiera informacje](#_mfcnotes_tn035_set_includes).

## <a name="analysis-of-appwizard-created-rc-and-h-files"></a>Analiza AppWizard-Created. RC i. Pliki H

Badanie kodu aplikacji utworzonego przez AppWizard zawiera szczegółowe informacje dotyczące sposobu, w jaki Visual C++ zarządza wielu plików zasobów i plików nagłówkowych. Fragmenty kodu zbadane poniżej pochodzą z aplikacji MOJAAPL utworzonej przez AppWizard przy użyciu opcji domyślnych.

Aplikacja utworzona przez AppWizard używa wielu plików zasobów i wielu plików nagłówkowych, jak przedstawiono na poniższym diagramie:

```Diagram
   RESOURCE.H     AFXRES.H
          \       /
           \     /
          MYAPP.RC
              |
              |
        RES\MYAPP.RC2
        AFXRES.RC
        AFXPRINT.RC
```

Te relacje wielu plików można wyświetlić za pomocą polecenia Visual C++ plik/zestaw zawiera.

MojaApl. Zwrot
Plik zasobów aplikacji, który edytujesz przy użyciu Visual C++.

Zasoby. H to plik nagłówka specyficzny dla aplikacji. Zawsze ma nazwę zasób. H przez AppWizard spójny z domyślnym nazewnictwem pliku nagłówkowego Visual C++. #Include dla tego pliku nagłówkowego jest pierwszą instrukcją w pliku zasobów (MOJAAPL. RC):

```rc
//Microsoft Visual C++ generated resource script
//
#include "resource.h"
```

RES\MYAPP. Wersji
Zawiera zasoby, które nie będą edytowane przez Visual C++, ale zostaną uwzględnione w końcowej kompilacji. Plik EXE. AppWizard domyślnie nie tworzy takich zasobów, ponieważ Visual C++ może edytować wszystkie zasoby standardowe, w tym zasób wersji (nową funkcję w tej wersji). Pusty plik jest generowany przez AppWizard w przypadku dodania własnych niestandardowych zasobów sformatowanych do tego pliku.

Jeśli używasz niestandardowych zasobów sformatowanych, możesz dodać je do RES\MYAPP. RC2 i edytuj je przy użyciu edytora tekstu Visual C++.

Plik AFXRES. RC i AFXPRINT. RC zawiera zasoby standardowe wymagane przez niektóre funkcje platformy. Like RES\MYAPP. RC2 te dwa pliki zasobów udostępniane przez platformę są #include do końca MOJAAPL. RC i są one określone w dyrektywach Compile-Time okna dialogowego zestaw zawiera. W ten sposób nie można bezpośrednio wyświetlać ani edytować tych zasobów platformy podczas edytowania programu MOJAAPL. RC w Visual C++, ale są one kompilowane do pliku binarnego aplikacji. Plik RES i ostatni. Plik EXE. Aby uzyskać więcej informacji na temat standardowych zasobów platformy, w tym procedur ich modyfikacji, zobacz [Uwagi techniczne 23](../mfc/tn023-standard-mfc-resources.md).

Plik AFXRES. H definiuje standardowe symbole, takie jak `ID_FILE_NEW` , używane przez platformę i używane w plik AFXRES. Zwrot. Plik AFXRES. H również #include WINREs. H, która zawiera Podzestaw systemu WINDOWS. H, które są zbędne przez Visual C++ wygenerowany. RC, a także plik AFXRES. Zwrot. Symbole zdefiniowane w plik AFXRES. H są dostępne podczas edytowania pliku zasobów aplikacji (MOJAAPL. RC). Na przykład, `ID_FILE_NEW` jest używany dla elementu menu nowy plik w programie MojaApl. Zasób menu RC. Nie można zmienić ani usunąć tych symboli zdefiniowanych przez strukturę.

## <a name="including-additional-header-files"></a><a name="_mfcnotes_tn035_including"></a> Dołączanie dodatkowych plików nagłówkowych

Aplikacja utworzona AppWizard zawiera tylko dwa pliki nagłówkowe: RESOURCE. H i plik AFXRES. H. Tylko zasób. H to specyficzne dla aplikacji. Może być konieczne dołączenie dodatkowych plików nagłówkowych tylko do odczytu w następujących przypadkach:

Plik nagłówkowy jest dostarczany przez zewnętrzne źródło lub chcesz udostępnić plik nagłówkowy między wieloma projektami lub wieloma częściami tego samego projektu.

Plik nagłówkowy ma formatowanie i komentarze, których nie chcesz Visual C++ zmienić ani odfiltrować podczas zapisywania pliku. Na przykład może być konieczne zachowanie #define, która używa symbolicznej arytmetycznej, takiej jak:

```h
#define RED 0
#define BLUE 1
#define GREEN 2
#define ID_COLOR_BUTTON 1001
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)
```

Możesz dołączyć dodatkowe pliki nagłówkowe tylko do odczytu za pomocą polecenia **zasób zawiera** , aby określić instrukcję #include jako drugą dyrektywę symbol Read-Only, jak w:

```rc
#include "afxres.h"
#include "second.h"
```

Nowy Diagram relacji plików wygląda teraz następująco:

```Diagram
                   AFXRES.H
    RESOURCE.H     SECOND.H
          \       /
           \     /
          MYAPP.RC
              |
              |
        RES\MYAPP.RC2  
        AFXRES.RC
        AFXPRINT.RC
```

## <a name="sharing-a-header-file-between-two-rc-files"></a>Udostępnianie pliku nagłówka między dwoma. RC — pliki

Możesz chcieć udostępnić plik nagłówka między dwoma. RC pliki, które znajdują się w różnych projektach, lub prawdopodobnie w tym samym projekcie. W tym celu wystarczy zastosować opisaną powyżej technikę Read-Only dyrektywy do obu. RC — pliki. W przypadku, gdy te dwa. Pliki RC są dla różnych aplikacji (różne projekty), wyniki są zilustrowane na poniższym diagramie:

```Diagram
     RESOURCE.H   AFXRES.H   RESOURCE.H  
    (for MYAPP1)  SECOND.H   (for MYAPP2)
          \       /     \       /
           \     /       \     /
          MYAPP1.RC      MYAPP2.RC
           /    \        /     \
          /      \      /       \
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2
                AFXPRINT.RC
```

Przypadek, w którym drugi plik nagłówkowy jest współużytkowany przez dwa. Pliki RC w tej samej aplikacji (projekt) zostały omówione poniżej.

## <a name="using-multiple-resource-files-in-the-same-project"></a>Używanie wielu plików zasobów w tym samym projekcie

Visual C++ i kompilator zasobów obsługuje wiele. RC pliki w tym samym projekcie za pomocą #include jednego z nich. Plik RC w innym. Dozwolone jest wielokrotne zagnieżdżanie. Istnieją różne przyczyny podzielenia zasobów projektu na wiele. RC — pliki:

- Łatwiejsze jest zarządzanie dużą liczbą zasobów wśród wielu członków zespołu projektu, jeśli zasoby zostaną podzielone na wiele. RC — pliki. Jeśli używasz pakietu zarządzania kontrolą źródła do wyewidencjonowywania plików i ewidencjonowania zmian, Podziel zasoby na wiele. Pliki RC zapewniają dokładniejszą kontrolę nad zarządzaniem zmianami zasobów.

- Jeśli chcesz użyć dyrektyw preprocesora, takich jak #ifdef, #endif i #define, w przypadku części zasobów należy je odizolować w zasobach tylko do odczytu, które będą kompilowane przez kompilator zasobów.

- Składnika. Pliki RC załadują i zapisują się szybciej w Visual C++ niż w jednym kompozytie. Plik RC.

- Jeśli chcesz zachować zasób z edytorem tekstu w formularzu czytelnym dla człowieka, należy pozostawić go w. Plik RC jest oddzielony od jednego Visual C++ edycji.

- Jeśli musisz zachować zdefiniowany przez użytkownika zasób w postaci binarnej lub tekstowej, który jest interpretowany przez inny wyspecjalizowany Edytor danych, należy pozostawić go w osobnym. Plik RC, dlatego Visual C++ nie zmienia formatu na dane szesnastkowe. Polu. W przypadku plików WAV (dźwięk) w zaawansowanej koncepcji MFC przykłady [SPEAKN](../overview/visual-cpp-samples.md) są dobrym przykładem.

Możesz #include sekundę. RC w dyrektywach Compile-Time w oknie dialogowym Zestaw zawiera:

```h
#include "res\myapp.rc2"  // non-Visual C++ edited resources
#include "second.rc"  // THE SECOND .RC FILE

#include "afxres.rc"  // Standard components
#include "afxprint.rc"  // printing/print preview resources
```

Wyniki są zilustrowane na poniższym diagramie:

```Diagram
   RESOURCE.H     AFXRES.H
          \       /
           \     /
          MYAPP.RC
              |
              |
        RES\MYAPP.RC2
        SECOND.RC  
        AFXRES.RC
        AFXPRINT.RC
```

Korzystając z Compile-Timech dyrektyw, można organizować zasoby Visual C++ do edycji i nieedytowalne. RC — pliki, w których znajduje się "Master" MOJAAPL. RC nie robi nic, ale #include innych. RC — pliki. Jeśli używasz projektu języka Visual Studio C++. Plik MAK, należy uwzględnić "Master". Plik RC w projekcie, aby wszystkie #include zasoby były kompilowane z aplikacją.

## <a name="enforcement-of-noneditable-visual-c-files"></a>Wymuszanie nieedytowalnych plików Visual C++

RES\MYAPP. utworzony przez AppWizard Plik RC2 to przykład pliku zawierającego zasoby, których *nie* chcesz przypadkowo odczytać do Visual C++ a następnie zapisać go z powrotem z informacjami o formatowaniu. Aby chronić przed tym, umieść następujące wiersze na początku RES\MYAPP. Plik RC2:

```rc2
#ifdef APSTUDIO_INVOKED
    #error this file is not editable by Visual C++
#endif //APSTUDIO_INVOKED
```

Gdy Visual C++ kompiluje. Plik RC, definiuje `APSTUDIO_INVOKED` i `RC_INVOKED` . Jeśli struktura plików utworzona przez AppWizard jest uszkodzona, a Visual C++ odczytuje wiersz #error powyżej, zgłasza błąd krytyczny i przerywa odczyt. Plik RC.

## <a name="managing-symbols-shared-by-multiple-visual-c-edited-rc-files"></a>Zarządzanie symbolami udostępnionymi przez wiele Visual C++ edytowane. RC — pliki

Dwa problemy powstają podczas dzielenia zasobów na wiele. Pliki RC, które chcesz edytować oddzielnie w Visual C++:

- Możesz chcieć udostępnić te same symbole dla wielu. RC — pliki.

- Należy Visual C++ unikać przypisywania tych samych wartości numerycznych ID różnym zasobom (symbolom).

Na poniższym diagramie przedstawiono organizację. RC i. H plików, które są związane z pierwszym problemem:

```Diagram
              MYAPP.RC
             /         \
            /           \
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H
     \    /    /      \   \    \
      \  /    /        \   \    \
      MYSTRS.RC         MYMENUS.RC
```

W tym przykładzie zasoby ciągów są przechowywane w jednym pliku zasobów, MYSTRS. RC, a menu są przechowywane w innych MENU. Zwrot. Niektóre symbole, takie jak dla poleceń, mogą wymagać udostępnienia między dwoma plikami. Na przykład ID_TOOLS_SPELL może być IDENTYFIKATORem polecenia menu dla elementu pisownia w menu Narzędzia. może również być IDENTYFIKATORem ciągu wiersza polecenia wyświetlanego przez platformę na pasku stanu głównego okna aplikacji.

Symbol ID_TOOLS_SPELL jest przechowywany w udostępnionym pliku nagłówkowym, współdzielona. H. Ten udostępniony plik nagłówka można zachować ręcznie przy użyciu edytora tekstu. Visual C++ nie edytuje się bezpośrednio. W dwóch plikach zasobów MYSTRS. RC i webmenu. RC, należy określić #include. H w dyrektywach Read-Only dla programu MOJAAPL. RC, za pomocą polecenia **zasób zawiera** , zgodnie z wcześniejszym opisem.

Najlepiej jest przewidzieć symbol, który zostanie udostępniony przed podjęciem próby użycia go do zidentyfikowania dowolnego zasobu. Dodaj symbol do udostępnionego pliku nagłówkowego i, jeśli jeszcze nie #include pozostałego pliku nagłówkowego w dyrektywach Read-Only dla. Plik RC, zrób to przed użyciem symbolu. Jeśli nie przewidujesz udostępniania symbolu w ten sposób, musisz ręcznie (przy użyciu edytora tekstów) przenieść instrukcję #define dla symbolu z, powiedzmy. H do współdzielenia. H przed użyciem go w MYSTRS. Zwrot.

W przypadku zarządzania symbolami w wielu. RC należy również pomóc Visual C++ unikać przypisywania tych samych wartości numerycznych identyfikatorów do różnych zasobów (symboli). Dla każdego z nich. Plik RC, Visual C++ przyrostowo przypisuje identyfikatory w każdej z czterech domen identyfikatorów. Między edytowaniem sesji Visual C++ śledzi ostatni Identyfikator przypisany w każdej domenie w pliku nagłówkowym symboli dla. Plik RC. Poniżej przedstawiono wartości APS_NEXT dla pustego (nowego). Plik RC:

```rc
#define _APS_NEXT_RESOURCE_VALUE  101
#define _APS_NEXT_COMMAND_VALUE   40001
#define _APS_NEXT_CONTROL_VALUE   1000
#define _APS_NEXT_SYMED_VALUE     101
```

`_APS_NEXT_RESOURCE_VALUE` jest następną wartością symboliczną, która będzie używana dla zasobu okna dialogowego, zasobu menu i tak dalej. Prawidłowy zakres wartości symboli zasobów wynosi od 1 do 0x6FFF.

`_APS_NEXT_COMMAND_VALUE` jest następną wartością symboliczną, która będzie używana do identyfikacji polecenia. Prawidłowy zakres wartości symboli poleceń to 0x8000 do 0xDFFF.

`_APS_NEXT_CONTROL_VALUE` jest następną wartością symboliczną, która będzie używana dla kontrolki okna dialogowego. Prawidłowy zakres dla wartości symboli kontrolki okna dialogowego to 8 do 0xDFFF.

`_APS_NEXT_SYMED_VALUE` jest następną wartością symboliczną, która zostanie wystawiona po ręcznym przypisaniu wartości symbolu przy użyciu nowego polecenia w przeglądarce symboli.

Visual C++ rozpoczyna się od nieco wyższych wartości, których najniższa wartość prawna podczas tworzenia nowego. Plik RC. AppWizard będzie również inicjować te wartości bardziej odpowiednie dla aplikacji MFC. Aby uzyskać więcej informacji na temat zakresów wartości identyfikatorów, zobacz [Uwaga techniczna 20](../mfc/tn020-id-naming-and-numbering-conventions.md).

Teraz za każdym razem, gdy tworzysz nowy plik zasobów, nawet w tym samym projekcie, Visual C++ definiuje te same `_APS_NEXT_` wartości. Oznacza to, że w przypadku dodawania, mówiąc, wielu okien dialogowych w dwóch różnych. RC, że ta sama wartość #define zostanie przypisana do różnych okien dialogowych. Na przykład IDD_MY_DLG1 w pierwszej kolejności. Plik RC może mieć przypisaną taką samą liczbę 101, jak IDD_MY_DLG2 w drugim. Plik RC.

Aby tego uniknąć, należy zarezerwować odrębny zakres liczbowy dla każdej z czterech domen identyfikatorów w odpowiednich. RC — pliki. W tym celu należy ręcznie zaktualizować `_APS_NEXT` wartości w każdym z. RC pliki **przed** rozpoczęciem dodawania zasobów. Na przykład, jeśli pierwszy. Plik RC używa wartości domyślnych `_APS_NEXT` , a następnie można przypisać `_APS_NEXT` do drugiej następujące wartości. Plik RC:

```rc
#define _APS_NEXT_RESOURCE_VALUE  2000
#define _APS_NEXT_COMMAND_VALUE   42000
#define _APS_NEXT_CONTROL_VALUE   2000
#define _APS_NEXT_SYMED_VALUE     2000
```

Oczywiście nadal jest możliwe, że Visual C++ przypisze tyle identyfikatorów w pierwszej kolejności. RC, że wartości liczbowe zaczynają nakładać się na zarezerwowanych dla drugiej. Plik RC. Należy zarezerwować wystarczająco duże zakresy, aby to nie miało miejsce.

## <a name="managing-dependencies-between-rc-cpp-and-h-files"></a>Zarządzanie zależnościami między. RC,. CPP i. Pliki H

Gdy Visual C++ zapisuje. Plik RC, zapisuje także zmiany symboli w odpowiednim zasobie. Plik H. Dowolna z nich. Pliki CPP odwołujące się do zasobów w programie. Plik RC musi #include zasób. H plik, zazwyczaj z poziomu głównego pliku nagłówkowego projektu. Prowadzi to do niepożądanego efektu ubocznego ze względu na wewnętrzne zarządzanie projektami środowiska programistycznego, które skanuje pliki źródłowe pod kątem zależności nagłówka. Za każdym razem, gdy dodasz nowy symbol w Visual C++, wszystkie. Pliki CPP, które #include zasób. Należy ponownie skompilować H.

Visual C++, omija zależność od zasobu. H przez uwzględnienie następującego komentarza jako pierwszego wiersza zasobu. Plik H:

```h
//{{NO_DEPENDENCIES}}
```

Środowisko programistyczne interpretuje ten komentarz poprzez ignorowanie zmian w zasobie. H, tak, aby była zależna. Nie trzeba ponownie kompilować plików CPP.

Visual C++ zawsze dodaje wiersz komentarza//{{NO_DEPENDENCIES}} do elementu. RC plik. W niektórych przypadkach obejście zależności kompilacji względem zasobu. H może prowadzić do błędów czasu wykonywania wykrytych w czasie łącza. Jeśli na przykład użyjesz przeglądarki symboli do zmiany wartości liczbowej przypisanej do symbolu zasobu, zasób nie zostanie prawidłowo znaleziony i załadowany w czasie wykonywania aplikacji, jeśli. Plik CPP odwołujący się do zasobu nie został ponownie skompilowany. W takich przypadkach należy jawnie ponownie skompilować wszystkie. Pliki CPP, na które wiadomo, mają wpływ zmiany symboli w zasobie. H lub wybierz opcję **Kompiluj ponownie wszystko**. Jeśli potrzebujesz często zmieniać wartości symboliczne dla określonej grupy zasobów, prawdopodobnie okaże się, że jest to bardziej wygodne i bezpieczniejsze, aby podzielić te symbole na osobny plik nagłówkowy tylko do odczytu, zgodnie z opisem w powyższej sekcji, w [tym o dodatkowych plikach nagłówkowych](#_mfcnotes_tn035_including).

## <a name="how-visual-c-manages-set-includes-information"></a><a name="_mfcnotes_tn035_set_includes"></a> Jak Visual C++ zarządzanie zestawem zawiera informacje

Jak wspomniano powyżej, zestaw menu plik zawiera polecenie umożliwia określenie trzech typów informacji:

- Plik nagłówka symboli

- Dyrektywy symboli Read-Only

- Dyrektywy Compile-Time

Poniżej opisano sposób, w jaki Visual C++ utrzymuje te informacje w. Plik RC. Te informacje nie są potrzebne do korzystania z Visual C++, ale mogą wzmocnić swoje zrozumienie, aby lepiej wykorzystać funkcję Set includes.

Każdy z powyższych trzech typów zestawu zawiera informacje są przechowywane w. Plik RC w dwóch formach: (1) jako #include lub inne dyrektywy interpretowane przez kompilator zasobów oraz (2) jako specjalne Zasoby TEXTINCLUDE interpretowane tylko przez Visual C++.

Celem zasobu TEXTINCLUDE jest bezpieczne przechowywanie zestawu informacji o dołączaniu w formularzu, który jest łatwo gotowy do użycia w oknie dialogowym **zestaw** Visual C++. TEXTINCLUDE to *Typ zasobu* zdefiniowany przez Visual C++. Visual C++ rozpoznaje trzy określone zasoby TEXTINCLUDE, które mają numery identyfikacyjne zasobów 1, 2 i 3:

|Identyfikator zasobu TEXTINCLUDE|Typ zestawu zawiera informacje|
|-----------------------------|--------------------------------------|
|1|Plik nagłówka symboli|
|2|Dyrektywy symboli Read-Only|
|3|Dyrektywy Compile-Time|

Każdy z trzech typów zestawu zawiera informacje, które są zilustrowane przez domyślny MOJAAPL. RC i RESOURCE. H plików utworzonych przez AppWizard, zgodnie z poniższym opisem. Tokeny ekstra \ 0 i "" między blokami BEGIN i END są wymagane przez składnię RC, aby określić zero zakończonych ciągów i znak cudzysłowu.

### <a name="symbol-header-file"></a>Plik nagłówka symboli

Forma informacji o pliku nagłówkowym symboli interpretowana przez kompilator zasobów jest po prostu instrukcją #include:

```rc
#include "resource.h"
```

Odpowiedni zasób TEXTINCLUDE to:

```rc
1 TEXTINCLUDE DISCARDABLE
BEGIN
    "resource.h\0"
END
```

### <a name="read-only-symbol-directives"></a>Dyrektywy symboli Read-Only

Dyrektywy symboli Read-Only są zawarte w górnej części MOJAAPL. RC w następującej formie interpretowanej przez kompilator zasobów:

```rc
#include "afxres.h"
```

Odpowiedni zasób TEXTINCLUDE to:

```rc
2 TEXTINCLUDE DISCARDABLE
BEGIN
   "#include ""afxres.h""\r\n"
   "\0"
END
```

### <a name="compile-time-directives"></a>Dyrektywy Compile-Time

Dyrektywy Compile-Time są zawarte na końcu MOJAAPL. RC w następującej formie interpretowanej przez kompilator zasobów:

```rc
#ifndef APSTUDIO_INVOKED
///////////////////////
//
// From TEXTINCLUDE 3
//
#include "res\myapp.rc2"  // non-Visual C++ edited resources

#include "afxres.rc"  // Standard components
#include "afxprint.rc"  // printing/print preview resources
#endif  // not APSTUDIO_INVOKED
```

Dyrektywa APSTUDIO_INVOKED #ifndef instruuje Visual C++, aby pominąć dyrektywy Compile-Time.

Odpowiedni zasób TEXTINCLUDE to:

```rc
3 TEXTINCLUDE DISCARDABLE
BEGIN
"#include ""res\myapp.rc2""  // non-Visual C++ edited resources\r\n"
"\r\n"
"#include ""afxres.rc""  // Standard components\r\n"
"#include ""afxprint.rc""  // printing/print preview resources\r\n"
"\0"
END
```

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)\
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
