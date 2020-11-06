---
title: Jak zgłosić problem z zestawem narzędzi platformy Microsoft C++
description: Jak utworzyć dobry raport o problemie i Odtwórz informacje dotyczące zestawu narzędzi Microsoft C++.
ms.date: 09/24/2019
ms.technology: cpp-ide
author: corob-msft
ms.author: corob
ms.openlocfilehash: 7a89966b46efbef9800f3f3ddf836723bbb3b06f
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334250"
---
# <a name="how-to-report-a-problem-with-the-microsoft-c-toolset-or-documentation"></a>Jak zgłosić problem z zestawem narzędzi lub dokumentacją języka Microsoft C++

Jeśli znajdziesz problemy w kompilatorze Microsoft C++ (MSVC), konsolidatorze lub innych narzędziach i bibliotekach, chcemy wiedzieć o nich. Gdy problem znajduje się w naszej dokumentacji, chcemy wiedzieć o tym.

## <a name="how-to-report-a-c-toolset-issue"></a>Jak zgłosić problem z zestawem narzędzi języka C++

Najlepszym sposobem, aby poinformować nas o problemie, jest wysłanie nam raportu zawierającego opis wykrytego problemu. Powinien on zawierać wszystkie szczegółowe informacje o sposobie tworzenia programu. Powinien on zawierać *Odtwórz* , kompletny przypadek testowy, którego można użyć do odtworzenia problemu na własnych maszynach. Te informacje pozwalają nam szybko sprawdzić, czy problem występuje w naszym kodzie i nie jest lokalny dla Twojego środowiska. Pomaga nam w ustaleniu, czy ma wpływ na inne wersje kompilatora i zdiagnozować jego przyczynę.

W poniższych sekcjach znajdziesz informacje o tym, co robi dobry raport. Opisujemy, jak generować Odtwórz dla rodzaju wykrytego problemu oraz jak wysyłać raporty do zespołu produktów. Twoje raporty są ważne dla nas i dla innych deweloperów, takich jak ty. Dziękujemy za pomóc nam ulepszyć program Microsoft C++!

## <a name="how-to-prepare-your-report"></a>Jak przygotować raport

Ważne jest, aby utworzyć raport wysokiej jakości, ponieważ trudno jest odtworzyć znaleziony problem bez kompletnych informacji. Im lepszy raport to, tym bardziej efektywnie możemy odtworzyć i zdiagnozować problem.

Raport powinien zawierać co najmniej następujące wartości:

- Pełne informacje o wersji zestawu narzędzi, którego używasz.

- Pełny cl.exe wiersz polecenia służący do kompilowania kodu.

- Szczegółowy opis znalezionego problemu.

- Odtwórz: kompletny, uproszczony, z własnym przykładem kod źródłowy, który pokazuje problem.

Przeczytaj, aby dowiedzieć się więcej o konkretnych informacjach, których potrzebujemy, i skąd można ją znaleźć oraz jak utworzyć dobry Odtwórz.

### <a name="the-toolset-version"></a>Wersja zestawu narzędzi

Potrzebujemy pełnej informacji o wersji i architektury docelowej zestawu narzędzi, który powoduje problem. Dzięki temu możemy testować Odtwórz na tym samym zestawie narzędzi na naszych komputerach. Jeśli będziemy mogli odtworzyć ten problem, te informacje będą również wskazywały na rozpoczęcie badania, które inne wersje zestawu narzędzi mają ten sam problem.

#### <a name="to-report-the-full-version-of-your-compiler"></a>Aby zgłosić pełną wersję kompilatora

1. Otwórz **wiersz polecenia dla deweloperów** , które pasują do wersji programu Visual Studio i architektury konfiguracji użytej do skompilowania projektu. Na przykład, Jeśli kompilujesz przy użyciu programu Visual Studio 2017 na platformie x64 dla elementów docelowych x64, wybierz **wiersz polecenia narzędzi x64 Native Tools dla programu VS 2017**. Aby uzyskać więcej informacji, zobacz [skróty do wiersza polecenia dla deweloperów](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts).

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **CL/BV**.

Dane wyjściowe powinny wyglądać podobnie do:

```Output
C:\Users\username\Source>cl /Bv
Microsoft (R) C/C++ Optimizing Compiler Version 19.14.26428.1 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

Compiler Passes:
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\cl.exe:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1xx.dll:      Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c2.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\link.exe:      Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\mspdb140.dll:  Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\1033\clui.dll: Version 19.14.26428.1

cl : Command line error D8003 : missing source filename
```

Skopiuj i wklej całe dane wyjściowe do raportu.

### <a name="the-command-line"></a>Wiersz polecenia

Potrzebujemy dokładnego wiersza polecenia, cl.exe i wszystkich argumentów używanych do kompilowania kodu. Dzięki temu możemy skompilować ją w taki sam sposób na naszych komputerach. Ważne, ponieważ znaleziony problem może wystąpić tylko w przypadku kompilowania z określonym argumentem lub kombinacją argumentów.

Najlepsze miejsce na znalezienie tych informacji znajduje się w dzienniku kompilacji natychmiast po napotkaniu problemu. Zapewnia, że wiersz polecenia zawiera dokładnie te same argumenty, które mogą przyczynić się do problemu.

#### <a name="to-report-the-contents-of-the-command-line"></a>Aby zgłosić zawartość wiersza polecenia

1. Znajdź plik **CL. Command. 1. tlog** , a następnie otwórz go. Domyślnie ten plik znajduje się w folderze dokumenty w programie \\ Visual Studio *Version* \\ projects \\ *SolutionName* \\ *ProjectName* \\ *Configuration* \\ *ProjectName*. tlog \\ CL. Command. 1. tlog lub w folderze użytkownika w obszarze \\ repozytoria źródłowego resourceName \\ \\ *SolutionName* \\ *ProjectName* \\ *Configuration* \\ *ProjectName*. tlog \\ CL. Command. 1. tlog. Może znajdować się w innej lokalizacji, jeśli używasz innego systemu kompilacji lub zmieniono lokalizację domyślną dla projektu.

   Wewnątrz tego pliku znajdują się nazwy plików kodu źródłowego, a następnie argumenty wiersza polecenia używane do kompilowania, każdy w osobnych wierszach.

1. Znajdź wiersz, który zawiera nazwę pliku kodu źródłowego, w którym występuje problem. Wiersz poniżej zawiera odpowiednie argumenty polecenia cl.exe.

Skopiuj i wklej cały wiersz polecenia do raportu.

### <a name="a-description-of-the-problem"></a>Opis problemu

Potrzebujemy szczegółowego opisu znalezionego problemu. Dzięki temu możemy sprawdzić, czy na naszych komputerach widzimy ten sam efekt. Czasami warto również wiedzieć, co próbujesz zrobić, i czego oczekujesz.

Dobry opis zawiera **szczegółowe komunikaty o błędach** dostarczone przez zestaw narzędzi lub dokładne zachowanie środowiska uruchomieniowego, które widzisz. Potrzebujemy tych informacji, aby sprawdzić, czy problem został wystawiony prawidłowo. Uwzględnij **wszystkie** dane wyjściowe kompilatora, a nie tylko ostatni komunikat o błędzie. Musimy zobaczyć wszystko, co doprowadziło do zgłoszenia problemu. Jeśli problem można zduplikować przy użyciu kompilatora wiersza polecenia, to dane wyjściowe kompilatora są preferowane. Środowisko IDE i inne systemy kompilacji mogą odfiltrować wyświetlane komunikaty o błędach lub tylko przechwycić pierwszy wiersz komunikatu o błędzie.

Jeśli problem polega na tym, że kompilator akceptuje nieprawidłowy kod i nie generuje diagnostyki, należy uwzględnić to w raporcie.

Aby zgłosić problem z zachowaniem środowiska uruchomieniowego, należy podać **dokładną kopię** tego, co program drukuje, i oczekiwane informacje. Najlepszym rozwiązaniem jest osadzenie go w instrukcji Output, na przykład `printf("This should be 5: %d\n", actual_result);` . Jeśli program ulegnie awarii lub zawiesza się, należy również wspomnieć o tym.

Dodaj inne szczegóły, które mogą pomóc nam w zdiagnozowaniu znalezionego problemu, na przykład w przypadku wszystkich wykrytych działań. Spróbuj nie powtarzać informacji znalezionych w innym miejscu raportu.

### <a name="the-repro"></a>Odtwórz

*Odtwórz* to kompletny, samodzielny przykład kodu źródłowego. Reproducibly IT demonstruje znaleziony problem, dlatego nazwę. Potrzebujemy elementu Odtwórz, aby można było odtworzyć błąd na naszych komputerach. Kod powinien być wystarczający do utworzenia podstawowego pliku wykonywalnego, który kompiluje i uruchamia. Lub, które *byłyby* skompilowane i uruchomione, jeśli nie dotyczy wykrytego problemu. Odtwórz nie jest fragmentem kodu. Powinien on mieć kompletną funkcję i klasy oraz zawierać wszystkie niezbędne dyrektywy #include, nawet dla standardowych nagłówków.

#### <a name="what-makes-a-good-repro"></a>Co robi dobry Odtwórz

Dobrym odtwórzem jest:

- **Mniejsze.** Reprofesjonalisty powinny być tak małe, jak to możliwe, jednak nadal pokazują dokładnie znaleziony problem. Reprofesjonalisty nie muszą być złożone ani realistyczne. Muszą oni tylko wyświetlić kod, który jest zgodny ze standardem lub do udokumentowanej implementacji kompilatora. W przypadku brakującej diagnostyki Odtwórz powinien pokazać kod, który nie jest zgodny. Proste, do-punktowe rozwiązania, które zawierają tylko wystarczającą ilość kodu do zademonstrowania problemu, są najlepsze. Jeśli możesz wyeliminować lub uprościć kod i zachować zgodność, a także pozostawić problem bez zmian, należy to zrobić. Nie trzeba dołączać licznika-przykłady kodu, który działa.

- **Samodzielny.** Reprofesjonalisty powinny unikać niepotrzebnych zależności. Jeśli problem można odtworzyć bez bibliotek innych firm, należy to zrobić. Jeśli problem można odtworzyć bez kodu biblioteki oprócz prostych instrukcji wyjściowych (na przykład,, `puts("this shouldn't compile");` `std::cout << value;` i `printf("%d\n", value);` ), zrób to. Jest to idealne rozwiązanie, jeśli przykład może zostać skrócony do pojedynczego pliku kodu źródłowego bez odwołania do żadnego nagłówka użytkownika. Zmniejszenie ilości kodu, który należy wziąć pod uwagę jako możliwy współautor problemu, jest w sposób nieużyteczny dla nas.

- **Względem najnowszej wersji kompilatora.** Recenty powinny używać najnowszej aktualizacji do najnowszej wersji zestawu narzędzi zawsze wtedy, gdy jest to możliwe. Można też użyć najnowszej wersji wstępnej następnej aktualizacji lub następnego wydania. Problemy, które mogą znajdować się w starszych wersjach zestawu narzędzi, często zostały rozwiązane w nowszych wersjach. Poprawki są przełączone do starszych wersji tylko w wyjątkowych okolicznościach.

- **Sprawdzane względem innych kompilatorów** , jeśli są odpowiednie. Reprofesjonalisty obejmujące kod Portable C++ powinny weryfikować zachowanie w przypadku innych kompilatorów, jeśli jest to możliwe. Standard C++ ostatecznie określa prawidłowość programu i żaden kompilator nie jest idealny. Jednak w przypadku gdy Clang i w zatoce zaakceptują swój kod bez diagnostyki, a MSVC nie, prawdopodobnie znaleziono usterkę w naszym kompilatorze. (Inne możliwości obejmują różnice w działaniu systemu UNIX i Windows albo różne poziomy implementacji standardu C++ itd.) Gdy wszystkie kompilatory odrzucają kod, prawdopodobnie kod jest nieprawidłowy. Wyświetlanie różnych komunikatów o błędach może ułatwić zdiagnozowanie problemu.

   Możesz znaleźć listę kompilatorów online, aby przetestować swój kod w [kompilatorach online c++](https://isocpp.org/blog/2013/01/online-c-compilers) w witrynie internetowej ISO c++ lub na nienadzorowanej [liście kompilatorów online c++](https://arnemertz.github.io/online-compilers/) w serwisie GitHub. Niektóre konkretne przykłady to [Wandbox](https://wandbox.org/), [Eksplorator kompilatora](https://godbolt.org/)i [Coliru](https://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Witryny sieci Web kompilatora online nie są powiązane z firmą Microsoft. Wiele witryn sieci Web kompilatora online jest uruchomionych jako projekty osobiste. Niektóre z tych witryn mogą być niedostępne podczas czytania, ale wyszukiwanie powinno znaleźć inne, których można użyć.

Problemy w kompilatorze, konsolidatorze i w bibliotekach, które mają na celu pokazanie siebie w określony sposób. Rodzaj znalezionego problemu określi, jakiego rodzaju Odtwórz należy uwzględnić w raporcie. Bez odpowiedniej Odtwórz nie mamy nic do zbadania. Poniżej przedstawiono kilka rodzajów problemów, które mogą zostać wyświetlone. Zawieramy instrukcje dotyczące sposobu generowania rodzaju Odtwórz, którego należy użyć do zgłaszania każdego rodzaju problemu.

#### <a name="frontend-parser-crash"></a>Awaria frontonu (analizator)

Awarie frontonu występują podczas fazy analizy kompilatora. Zazwyczaj kompilator emituje [błąd krytyczny C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)i odwołuje się do pliku kodu źródłowego oraz numeru wiersza, na którym wystąpił błąd. Często wymienia plik o nazwie MSC1. cpp, ale można zignorować te szczegóły.

W przypadku tego rodzaju awarii należy zapewnić [wstępnie przetworzony Odtwórz](#preprocessed-repros).

Oto przykładowe dane wyjściowe kompilatora dla tego rodzaju awarii:

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>Awaria zaplecza (generowanie kodu)

Awarie zaplecza występują podczas fazy generowania kodu kompilatora. Zazwyczaj kompilator emituje [błąd krytyczny C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)i nie odwołuje się do pliku kodu źródłowego i numeru wiersza skojarzonego z problemem. Często wspominany jest plik \\ UTC \\ src \\ P2 \\ Main. c, ale można zignorować te szczegóły.

W przypadku tego rodzaju awarii Podaj [link Odtwórz](#link-repros) , jeśli używasz generowania kodu w czasie konsolidacji (LTCG), który jest włączony przez argument wiersza polecenia **/GL** , aby cl.exe. W przeciwnym razie zamiast tego Podaj [wstępnie przetworzony Odtwórz](#preprocessed-repros) .

Oto przykładowe dane wyjściowe kompilatora dla awarii wewnętrznej bazy danych, w której LTCG nie jest używany. Jeśli dane wyjściowe kompilatora wyglądają jak poniżej, należy dostarczyć [wstępnie przetworzony Odtwórz](#preprocessed-repros).

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

Jeśli wiersz zaczynający się od **wewnętrznego błędu kompilatora** wymienia link.exe, a nie cl.exe, LTCG został włączony. W tym przypadku podaj [link Odtwórz](#link-repros) . Gdy nie jest jasne, czy LTCG został włączony z komunikatu o błędzie kompilatora, sprawdź argumenty wiersza polecenia. Skopiowano je z dziennika kompilacji w poprzednim kroku dla argumentu wiersza polecenia **/GL** .

#### <a name="linker-crash"></a>Awaria konsolidatora

Awarie konsolidatora występują w fazie konsolidacji po uruchomieniu kompilatora. Zwykle konsolidator wyemituje [Narzędzia konsolidatora LNK1000 błąd](../error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Jeśli dane wyjściowe wymieniają C1001 lub obejmują generowanie kodu w czasie konsolidacji, zapoznaj się z [Zaplecem (generowanie kodu)](#backend-code-generation-crash) .

W przypadku tego rodzaju awarii Podaj [link Odtwórz](#link-repros).

Oto przykład danych wyjściowych kompilatora dla tego rodzaju awarii:

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

Jeśli konsolidacja przyrostowa jest włączona, a awaria wystąpiła dopiero po pomyślnym nawiązaniu połączenia, to oznacza, że tylko po pierwszym pełnym łączu, na którym bazuje łącze przyrostowe, także udostępnieniu kopii plików obiektu (. obj) i biblioteki (lib), które odpowiadają plikom źródłowym zmodyfikowanym po zakończeniu pierwotnego linku.

#### <a name="bad-code-generation"></a>Złe generowanie kodu

Niewłaściwe generowanie kodu jest rzadkie. Występuje, gdy kompilator błędnie wygeneruje niepoprawny kod, który powoduje awarię aplikacji w czasie wykonywania. Zamiast tego należy wygenerować prawidłowy kod lub wykryć problem w czasie kompilacji. Jeśli uważasz, że znaleziony problem powoduje niewłaściwe generowanie kodu, zgłoś raport w taki sam sposób, jak [awaria zaplecza (generowanie kodu)](#backend-code-generation-crash).

W przypadku tego rodzaju awarii Podaj [link Odtwórz](#link-repros) , jeśli używasz argumentu wiersza polecenia **/GL** do cl.exe. Jeśli nie, podaj [wstępnie przetworzony Odtwórz](#preprocessed-repros) .

## <a name="how-to-generate-a-repro"></a>Jak wygenerować Odtwórz

Aby pomóc nam w śledzeniu źródła problemu, [dobrym odtwórzm](#what-makes-a-good-repro) jest istotna wartość. Przed wykonaniem któregokolwiek z kroków opisanych poniżej dla określonych rodzajów odniesień spróbuj odpowiednio zakodować kod, który pokazuje problem. Spróbuj wyeliminować lub zminimalizować zależności, wymagane nagłówki i biblioteki. Ogranicz opcje kompilatora i używane Definicje preprocesora, jeśli to możliwe.

Poniżej znajdują się instrukcje dotyczące generowania różnych rodzajów regeneracji, które będą używane do zgłaszania różnych rodzajów problemów.

### <a name="preprocessed-repros"></a>Wstępnie przetworzone wyprofesjonalisty

*Wstępnie przetworzony Odtwórz* jest pojedynczym plikiem źródłowym, który pokazuje problem. Jest generowany na podstawie danych wyjściowych preprocesora języka C. Aby go utworzyć, użyj opcji " **/p** kompilator" w oryginalnym pliku źródłowym Odtwórz. Ta opcja podkreśla zawarte nagłówki, aby usunąć zależności od dodatkowych plików źródłowych i nagłówków. Opcja rozwiązuje również problemy z makrami, #ifdefmi warunkowymi i innymi poleceniami preprocesora, które mogą być zależne od środowiska lokalnego.

> [!NOTE]
> Wstępnie przetworzone rozwiązania nie są tak przydatne w przypadku problemów, które mogą wynikać z błędów w naszej implementacji biblioteki standardowej, ponieważ często chcemy zastąpić najnowszą implementację w toku, aby sprawdzić, czy problem został już rozwiązany. W takim przypadku nie należy wstępnie przetworzyć Odtwórz, a jeśli problem nie zostanie zredukowany do pojedynczego pliku źródłowego, spakuj kod do pliku zip lub podobne lub Rozważ użycie Odtwórz projektu IDE. Aby uzyskać więcej informacji, zobacz [inne reformatyki](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Aby wstępnie przetworzyć plik kodu źródłowego

1. Przechwyć argumenty wiersza polecenia używane do kompilowania Odtwórz, zgodnie z opisem w artykule [Aby zgłosić zawartość wiersza polecenia](#to-report-the-contents-of-the-command-line).

1. Otwórz **wiersz polecenia dla deweloperów** , które pasują do wersji programu Visual Studio i architektury konfiguracji użytej do skompilowania projektu.

1. Przejdź do katalogu, który zawiera projekt Odtwórz.

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **CL/p** *argumenty* *filename. cpp*. Dla *argumentów* Użyj listy przechwyconych powyżej argumentów. *filename. cpp* to nazwa pliku źródłowego Odtwórz. To polecenie replikuje wiersz polecenia, który został użyty w Odtwórz, ale kończy kompilację po przejściu preprocesora. Następnie zapisuje wstępnie przetworzony kod źródłowy do *filename. i*.

Jeśli przetwarzasz wstępnie plik kodu źródłowego C++/CX lub używasz funkcji modułów języka C++, wymagane są pewne dodatkowe czynności. Aby uzyskać więcej informacji, zobacz poniższe sekcje.

Po wygenerowaniu wstępnie przygotowanego pliku dobrym pomysłem jest upewnienie się, że problem nadal odbędzie się w przypadku kompilowania wstępnie przygotowanego pliku.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Aby potwierdzić, że wstępnie przetworzony plik nadal wystanowił problem

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **CL** *argumentus* **/TP** *filename. i* , aby powiedzieć cl.exe, aby skompilować wstępnie przetworzony plik jako plik źródłowy języka C++. *Argumenty* są tymi samymi argumentami, które zostały przechwycone powyżej, ale z usuniętymi argumentami **/d** i **/i** . Wynika to z faktu, że zostały one już zawarte w wstępnie przetworzonym pliku. *filename. i* jest nazwą wstępnie przetworzonego pliku.

1. Upewnij się, że problem został odtworzony.

Na koniec Dołącz wstępnie przetworzony *plik* Odtwórz do raportu.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Wstępnie przetworzony kod w języku C++/CX WinRT/platformy UWP

Jeśli używasz języka C++/CX do kompilowania pliku wykonywalnego, musisz wykonać kilka dodatkowych kroków, aby utworzyć i zweryfikować wstępnie przetworzony Odtwórz.

#### <a name="to-preprocess-ccx-source-code"></a>Aby wstępnie przetworzyć kod źródłowy języka C++/CX

1. Utwórz wstępnie przetworzony plik źródłowy zgodnie z opisem w artykule, [Aby wstępnie przetworzyć plik kodu źródłowego](#to-preprocess-a-source-code-file).

1. Przeszukaj plik wygenerowanej _nazwy_ pliku. i dla dyrektyw **#using** .

1. Utwórz listę wszystkich plików, do których istnieją odwołania. Pozostaw wszystkie \* pliki. winmd systemu Windows, pliki platform. winmd i mscorlib.dll.

Aby przygotować się do zweryfikowania, że wstępnie przetworzony plik nadal powoduje problem,

1. Utwórz nowy katalog dla wstępnie przetworzonego pliku i skopiuj go do nowego katalogu.

1. Skopiuj pliki winmd z listy **#using** do nowego katalogu.

1. Utwórz pusty plik vccorlib. h w nowym katalogu.

1. Edytuj wstępnie przetworzony plik, aby usunąć wszystkie **#using** dyrektywy mscorlib.dll.

1. Przeprowadź edycję wstępnie przetworzonego pliku, aby zmienić wszystkie ścieżki bezwzględne na tylko nazwy plików. winmd.

Upewnij się, że wstępnie przetworzony plik nadal powoduje problem, jak powyżej.

### <a name="preprocessed-c-modules-repros"></a>Wstępnie przetworzone moduły w języku C++

Jeśli używasz funkcji modułów kompilatora języka C++, istnieją pewne różne kroki, które należy wykonać, aby utworzyć i zweryfikować wstępnie przetworzony Odtwórz.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Aby wstępnie przetworzyć plik kodu źródłowego, który używa modułu

1. Przechwyć argumenty wiersza polecenia używane do kompilowania Odtwórz, zgodnie z opisem w artykule [Aby zgłosić zawartość wiersza polecenia](#to-report-the-contents-of-the-command-line).

1. Otwórz **wiersz polecenia dla deweloperów** , które pasują do wersji programu Visual Studio i architektury konfiguracji użytej do skompilowania projektu.

1. Przejdź do katalogu, który zawiera projekt Odtwórz.

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **CL/p** *argumenty* *filename. cpp*. *Argumenty* są przechwyconych powyżej argumentów, a *filename. cpp* jest nazwą pliku źródłowego, który korzysta z modułu.

1. Przejdź do katalogu, który zawiera projekt Odtwórz, który skompilowano interfejs modułu (dane wyjściowe IFC).

1. Przechwyć argumenty wiersza polecenia użyte do skompilowania interfejsu modułu.

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **CL/p** *argumenty* *ModuleName. IXX*. *Argumenty* są przechwyconych powyżej argumentów, a wartość *ModuleName. IXX* jest nazwą pliku, który tworzy interfejs modułu.

Po wygenerowaniu wstępnie przetworzonych plików dobrym pomysłem jest upewnienie się, że problem nadal odbędzie się w przypadku użycia wstępnie przetworzonego pliku.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Aby potwierdzić, że wstępnie przetworzony plik nadal wystanowił problem

1. W oknie konsoli dewelopera Wróć do katalogu, który zawiera projekt Odtwórz.

1. Wprowadź wartość parametru **CL** *argumenty* **/TP** polecenie/lub, jak powyżej, aby skompilować wstępnie przetworzony plik, tak jakby był plikiem źródłowym języka *C++.*

1. Upewnij się, że problem jest nadal odtwarzany przez wstępnie przetworzony plik.

Na koniec Dołącz wstępnie przetworzone pliki Odtwórz ( *filename*. i i *ModuleName*. i) wraz z danymi wyjściowymi. IFC do raportu.

### <a name="link-repros"></a>Linki reinformatyków

*Link Odtwórz* to zawartość katalogu wygenerowanego przez konsolidatora, określona przez zmienną środowiskową **link \_ Odtwórz** lub jako argument dla opcji konsolidatora [/LINKREPRO](../build/reference/linkrepro.md) . Zawiera ona artefakty kompilacji, które zbiorczo przedstawiają problem występujący w czasie łączenia. Przykładami mogą być awarie zaplecza obejmujące generowanie kodu w czasie konsolidacji (LTCG) lub awarię konsolidatora. Te artefakty kompilacji są tymi, które są zbędne jako dane wejściowe konsolidatora, aby można było odtworzyć problem. Odtwórz linku można łatwo utworzyć przy użyciu tej zmiennej środowiskowej. Umożliwia wbudowaną funkcję generacji Odtwórz.

#### <a name="to-generate-a-link-repro-using-the-link_repro-environment-variable"></a>Aby wygenerować Odtwórz łącza przy użyciu zmiennej środowiskowej link_repro

1. Przechwyć argumenty wiersza polecenia używane do kompilowania Odtwórz, zgodnie z opisem w artykule [Aby zgłosić zawartość wiersza polecenia](#to-report-the-contents-of-the-command-line).

1. Otwórz **wiersz polecenia dla deweloperów** , które pasują do wersji programu Visual Studio i architektury konfiguracji użytej do skompilowania projektu.

1. W oknie konsoli wiersza polecenia dla deweloperów Przejdź do katalogu, który zawiera projekt Odtwórz.

1. Wprowadź **mkdir linkrepro** , aby utworzyć katalog o nazwie *linkrepro* dla łącza Odtwórz. Możesz użyć innej nazwy, aby przechwycić inne łącze Odtwórz.

1. Wprowadź **link Set \_ Odtwórz = linkrepro** , aby ustawić zmienną środowiskową **link \_ Odtwórz** do utworzonego katalogu. Jeśli kompilacja jest uruchamiana z innego katalogu, tak jak często jest to możliwe w przypadku bardziej złożonych projektów, a następnie zamiast tego należy ustawić **link \_ Odtwórz** na pełną ścieżkę do katalogu linku Odtwórz.

1. Aby skompilować projekt Odtwórz w programie Visual Studio, w oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **devenv**. Gwarantuje to, że wartość zmiennej środowiskowej **link \_ Odtwórz** jest widoczna dla programu Visual Studio. Aby skompilować projekt w wierszu polecenia, użyj argumentów wiersza polecenia przechwycone powyżej, aby zduplikować kompilację Odtwórz.

1. Skompiluj projekt Odtwórz i upewnij się, że wystąpił oczekiwany problem.

1. Zamknij program Visual Studio, jeśli został on użyty do wykonania kompilacji.

1. W oknie konsoli wiersza polecenia dla deweloperów wprowadź polecenie **Ustaw łącze \_ Odtwórz =** , aby wyczyścić zmienną środowiskową **link \_ Odtwórz** .

Na koniec Spakuj Odtwórz, kompresując cały katalog linkrepro do pliku zip lub podobne i dołącz go do raportu.

Opcja konsolidatora **/LINKREPRO** ma taki sam skutek jak zmienna środowiskowa **linku \_ Odtwórz** . Można użyć opcji [/LINKREPROTARGET](../build/reference/linkreprotarget.md) , aby określić nazwę do filtrowania dla wygenerowanego linku Odtwórz. Aby użyć **/LINKREPROTARGET** , należy również określić opcję konsolidatora **/out** .

#### <a name="to-generate-a-link-repro-using-the-linkrepro-option"></a>Aby wygenerować łącze Odtwórz przy użyciu opcji/LINKREPRO

1. Utwórz katalog do przechowywania linku Odtwórz. Odwołujemy się do pełnej ścieżki katalogu, którą utworzysz jako _ścieżkę katalogu_. Użyj podwójnego cudzysłowu wokół ścieżki, jeśli zawiera spacje.

1. Dodaj polecenie **/LINKREPRO:**_Directory-Path_ do wiersza polecenia konsolidatora. W programie Visual Studio Otwórz okno dialogowe **strony właściwości** dla projektu. Wybierz stronę właściwości **Konfiguracja właściwości**  >  **Linker**  >  **wiersza polecenia** konsolidatora. Następnie w polu **dodatkowe opcje** wprowadź wartość **/LINKREPRO:**_Directory-Path_ . Wybierz **przycisk OK** , aby zapisać zmiany.

1. Skompiluj projekt Odtwórz i upewnij się, że wystąpił oczekiwany problem.

Na koniec Utwórz pakiet Odtwórz przez skompresowanie całej _ścieżki katalogu_ Odtwórz katalogu w pliku zip lub podobnej, a następnie Dołącz do raportu.

### <a name="other-repros"></a>Inne reprofesjonalisty

Jeśli nie możesz zmniejszyć problemu do pojedynczego pliku źródłowego lub wstępnie przetworzonego Odtwórz, a problem nie wymaga linku Odtwórz, możemy zbadać projekt IDE. Wszystkie wskazówki dotyczące tworzenia dobrego Odtwórz nadal mają zastosowanie: kod powinien być minimalny i niezależny. Problem powinien wystąpić w naszych najnowszych narzędziach, a jeśli ma to zastosowanie, nie powinien być widoczny w innych kompilatorach.

Utwórz Odtwórz jako minimalny projekt IDE, a następnie spakuj go, kompresując całą strukturę katalogów do pliku zip lub podobną i dołączając ją do raportu.

## <a name="ways-to-send-your-report"></a>Sposoby wysyłania raportu

Masz kilka dobrych metod uzyskiwania raportu do nas. Możesz użyć wbudowanego raportu programu Visual Studio, [Narzędzia problemu](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)lub strony [społeczności deweloperów programu Visual Studio]( https://aka.ms/feedback/report?space=62) . W dolnej części tej strony znajduje się również przycisk **opinii o produkcie** . Wybór zależy od tego, czy chcesz używać wbudowanych narzędzi w IDE do przechwytywania zrzutów ekranu i organizowania raportu. Jeśli wolisz nie, możesz bezpośrednio korzystać z witryny internetowej społeczności deweloperów.

> [!NOTE]
> Niezależnie od tego, jak przesyłasz raport, firma Microsoft szanuje Twoją prywatność. Firma Microsoft jest zobowiązana do zgodności ze wszystkimi przepisami i przepisami dotyczącymi ochrony prywatności danych. Aby dowiedzieć się, jak traktujemy dane wysyłane do nas, zobacz [zasady zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).

### <a name="use-the-report-a-problem-tool"></a>Korzystanie z narzędzia Zgłoś problem

Narzędzie **Zgłoś problem** w programie Visual Studio umożliwia użytkownikom programu Visual Studio zgłaszanie problemów za pomocą zaledwie kilku kliknięć. Zostanie wystawiony prosty formularz umożliwiający wysłanie szczegółowych informacji o znalezionym problemie. Następnie można przesłać raport bez opuszczania środowiska IDE.

Raportowanie problemu za pomocą narzędzia **Zgłoś problem** jest łatwe i wygodne w środowisku IDE. Możesz uzyskać do niego dostęp z paska tytułu, wybierając ikonę **Wyślij opinię** obok pola wyszukiwania **Szybkie uruchamianie** . Możesz też znaleźć go na pasku menu, aby **Help**  >  **wysłać opinię**  >  **Zgłoś problem**.

Gdy zdecydujesz się zgłosić problem, najpierw Przeszukaj społeczność deweloperów pod kątem podobnych problemów. Jeśli Twój problem został zgłoszony wcześniej, przekazanie raportu i dodanie komentarzy z dodatkowymi szczegółami. Jeśli nie widzisz podobnego problemu, wybierz przycisk **zgłoś nowy problem** u dołu okna dialogowego opinii programu Visual Studio i postępuj zgodnie z instrukcjami, aby zgłosić problem.

### <a name="use-the-visual-studio-developer-community-pages"></a>Korzystanie ze stron społeczności deweloperów programu Visual Studio

Strony społeczności deweloperów programu Visual Studio to kolejną wygodną metodę zgłaszania problemów i znajdowania rozwiązań dla programu Visual Studio oraz kompilatora, narzędzia i biblioteki języka C++. Istnieją konkretne strony społeczności deweloperów dla [programu Visual Studio](https://aka.ms/feedback/report?space=8), [Visual Studio dla komputerów Mac](https://aka.ms/feedback/report?space=41), [.NET](https://aka.ms/feedback/report?space=61), [C++](https://aka.ms/feedback/report?space=62), [Azure DevOps](https://aka.ms/feedback/report?space=21)i [Azure DevOps Server](https://aka.ms/feedback/report?space=22).

Poniżej kart społeczności w górnej części każdej strony jest pole wyszukiwania. Można go użyć, aby znaleźć wpisy, które zgłaszają problemy podobne do Twoich potrzeb. Rozwiązanie lub inne przydatne informacje związane z Twoim problemem są już dostępne. Jeśli ktoś zgłosił ten sam problem przed, należy zagłosować i skomentować ten raport zamiast tworzyć nowy raport o problemie. Aby skomentować, zagłosować lub zgłosić nowy problem, może zostać wyświetlony monit o zalogowanie się do konta programu Visual Studio. Gdy logujesz się po raz pierwszy, musisz wyrazić zgodę na uzyskanie dostępu do Twojego profilu aplikacji społeczności deweloperów.

W przypadku problemów z kompilatorem C++, konsolidatorem i innymi narzędziami i bibliotekami należy najpierw przeszukać stronę [społeczność deweloperów języka c++](https://aka.ms/vsfeedback/browsecpp) . Jeśli wyszukasz problem i nie został on zgłoszony wcześniej, wybierz przycisk **Zgłoś problem** obok pola wyszukiwania. Możesz dołączyć kod Odtwórz i wiersz polecenia, zrzuty ekranu, linki do powiązanych dyskusji i inne informacje, które Twoim zdaniem są odpowiednie i przydatne.

> [!TIP]
> W przypadku innych rodzajów problemów, które mogą znajdować się w programie Visual Studio, które nie są związane z zestawem narzędzi języka C++ (na przykład problemy z interfejsem użytkownika, uszkodzone funkcje IDE lub ogólne awarie), użyj narzędzia **Zgłoś problem** w środowisku IDE. Jest to najlepszy wybór ze względu na możliwości zrzutu ekranu i możliwości rejestrowania akcji interfejsu użytkownika, które prowadzą do znalezionego problemu. Te rodzaje błędów można również wyszukać w witrynie [społeczności deweloperów](https://aka.ms/feedback/report?space=8) programu Visual Studio. Aby uzyskać więcej informacji, zobacz [Jak zgłosić problem w programie Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

### <a name="reports-and-privacy"></a>Raporty i prywatność

**Wszystkie informacje w raportach i komentarze i odpowiedzi są publicznie widoczne domyślnie**. Zwykle jest to korzyść, ponieważ umożliwia całej społeczności przeglądanie problemów, rozwiązań i obejścia przez innych użytkowników. Jeśli jednak obawiasz się, że dane lub tożsamość są publiczne, w celu zachowania poufności lub własności intelektualnej są dostępne opcje.

Jeśli chodzi o ujawnienie tożsamości, [Utwórz nową konto Microsoft](https://signup.live.com/) , która nie ujawnia żadnych szczegółowych informacji o użytkowniku. Użyj tego konta, aby utworzyć raport.

**Nie umieszczaj żadnych elementów, które chcesz zachować prywatną w tytule lub treści raportu początkowego, który jest publiczny.** Zamiast tego należy powiedzieć, że dane będą wysyłane prywatnie w osobnym komentarzu. Aby upewnić się, że raport jest kierowany do odpowiednich osób, należy uwzględnić **cppcompiler** na liście tematów raportu o problemie. Po utworzeniu raportu o problemie można określić, kto może wyświetlać Twoje odpowiedzi i załączniki.

#### <a name="to-create-a-problem-report-for-private-information"></a>Aby utworzyć raport dotyczący problemu dla prywatnych informacji

1. W utworzonym raporcie wybierz pozycję **Dodaj komentarz** , aby utworzyć swój prywatny opis problemu.

1. W edytorze odpowiedzi użyj kontrolki lista rozwijana poniżej przycisków **Prześlij** i **Anuluj** , aby określić odbiorców odpowiedzi. Tylko określone osoby mogą wyświetlać te prywatne odpowiedzi i wszystkie obrazy, linki lub kod, które są w nich zawarte. Wybierz opcję **widoczne dla moderatorów i oryginalny plakat** , aby ograniczyć widoczność do pracowników firmy Microsoft i siebie.

1. Dodaj opis i wszelkie inne informacje, obrazy i załączniki plików potrzebne do Odtwórz. Wybierz przycisk **Prześlij** , aby wysłać te informacje prywatnie.

   Istnieje limit 2 GB załączonych plików i maksymalnie 10 plików. W przypadku większych przeciążeń Zażądaj adresu URL przekazywania w Twoim komentarzu prywatnym.

Wszystkie odpowiedzi w ramach tego komentarza mają tę samą widoczność z ograniczeniami. Jest ona prawdziwa nawet wtedy, gdy kontrolka listy rozwijanej na odpowiedzi nie pokazuje poprawnie stanu widoczności z ograniczeniami.

Aby zachować prywatność i zachować poufne informacje z widoku publicznego, należy zachować ostrożność. Zadbaj o to, aby cała interakcja z firmą Microsoft była odpowiedzią objętą komentarzem ograniczonym Odpowiedzi na inne komentarze mogą spowodować przypadkowe ujawnienie poufnych informacji.

## <a name="how-to-report-a-c-documentation-issue"></a>Jak zgłosić problem z dokumentacją języka C++

Problemy z usługą GitHub są używane do śledzenia problemów raportowanych w naszej dokumentacji. Problemy z usługą GitHub można teraz tworzyć bezpośrednio ze strony zawartości, co pozwala na korzystanie z znacznie bogatszego sposobu korzystania z autorów i zespołów produktów. Jeśli zobaczysz problem z dokumentem, jest to zły kod przykładowy, mylące wyjaśnienie, krytyczne pominięcie lub nawet literówka, możesz łatwo znać nas. Przewiń w dół strony i wybierz pozycję Zaloguj się, **Aby przekazać opinię dotyczącą dokumentacji**. Jeśli jeszcze tego nie zrobiono, musisz utworzyć konto usługi GitHub. Jeśli masz konto w usłudze GitHub, zobaczysz wszystkie nasze problemy z dokumentacją i ich stan. Otrzymasz również powiadomienia o wprowadzeniu zmian dotyczących zgłoszonego problemu. Aby uzyskać więcej informacji, zobacz [Nowy system opinii jest docs.Microsoft.com](/teamblog/a-new-feedback-system-is-coming-to-docs).

Problem z dokumentacją można utworzyć w witrynie GitHub, gdy jest używany przycisk opinii o dokumentacji. Problem jest automatycznie wypełniany przy użyciu pewnych informacji o stronie, na której został utworzony problem. Wiadomo, gdzie znajduje się problem, dlatego nie należy edytować tych informacji. Wystarczy dołączyć szczegóły dotyczące tego, co jest nieprawidłowe, a jeśli chcesz, sugerowaną poprawkę. [Nasze dokumenty w języku C++ są typu open source](https://github.com/MicrosoftDocs/cpp-docs/), więc jeśli chcesz samodzielnie przesłać poprawkę, możesz to zrobić. Aby uzyskać więcej informacji na temat sposobu współtworzenia dokumentacji, zapoznaj się z naszym [przewodnikiem](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) w witrynie GitHub.
