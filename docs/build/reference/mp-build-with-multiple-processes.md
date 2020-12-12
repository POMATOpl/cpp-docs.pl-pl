---
description: Dowiedz się więcej o:/MP (kompilacja z wieloma procesami)
title: /MP (Kompilacja z wieloma procesami)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.MultiProcessorCompilation
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.openlocfilehash: d5d4441be505dfc1251b099aa95a6ce1544289ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137790"
---
# <a name="mp-build-with-multiple-processes"></a>/MP (Kompilacja z wieloma procesami)

Opcja **/MP** może skrócić łączny czas kompilowania plików źródłowych w wierszu polecenia. Opcja **/MP** powoduje, że kompilator tworzy jedną lub więcej kopii siebie, każdy w osobnym procesie. Następnie te kopie jednocześnie kompilują pliki źródłowe. W związku z tym łączny czas kompilowania plików źródłowych można znacząco zmniejszyć.

## <a name="syntax"></a>Składnia

> **/MP**[*processMax*]

## <a name="arguments"></a>Argumenty

*processMax*<br/>
Obowiązkowe Maksymalna liczba procesów, które może utworzyć kompilator.

Argument *processMax* musi mieć wartość z zakresu od 1 do 65536. W przeciwnym razie kompilator emituje komunikat ostrzegawczy **D9014**, ignoruje argument *processMax* i przyjmuje maksymalną liczbę procesów wynoszącą 1.

Jeśli pominięto argument *processMax* , kompilator Pobiera liczbę [skutecznych procesorów](#effective_processors) na komputerze z systemu operacyjnego i tworzy proces dla każdego procesora.

## <a name="remarks"></a>Uwagi

Opcja kompilatora **/MP** może znacznie skrócić czas kompilacji podczas kompilowania wielu plików. Aby skrócić czas kompilacji, kompilator tworzy do *processMax* kopie samego siebie, a następnie używa tych kopii do kompilowania plików źródłowych w tym samym czasie. Opcja **/MP** ma zastosowanie do kompilacji, ale nie do konsolidacji lub generowania kodu w czasie konsolidacji. Domyślnie opcja **/MP** jest wyłączona.

Zwiększenie czasu kompilacji zależy od liczby procesorów na komputerze, liczby plików do skompilowania oraz dostępności zasobów systemowych, takich jak wydajność we/wy. Eksperymentuj z opcją **/MP** , aby określić najlepsze ustawienie do kompilowania określonego projektu. Aby uzyskać pomoc w podejmowaniu decyzji, zobacz [wytyczne](#guidelines).

## <a name="incompatible-options-and-language-features"></a>Niezgodne opcje i funkcje językowe

Opcja **/MP** jest niezgodna z niektórymi opcjami kompilatora i funkcjami językowymi. Jeśli użyjesz niezgodnej opcji kompilatora z opcją **/MP** , kompilator wystawia ostrzeżenie **D9030** i zignoruje opcję **/MP** . Jeśli używasz niezgodnej funkcji języka, kompilator wystawia błąd [C2813](../../error-messages/compiler-errors-2/compiler-error-c2813.md) , a następnie zakończy się lub kontynuuje w zależności od bieżącej opcji poziomu ostrzeżenia kompilatora.

> [!NOTE]
> Większość opcji jest niezgodnych, ponieważ w przypadku ich dozwolonych współbieżnie wykonywane kompilatory zapisują swoje dane wyjściowe jednocześnie do konsoli lub do określonego pliku. W związku z tym dane wyjściowe byłyby Intermix i zniekształcone. W niektórych przypadkach kombinacja opcji zwiększa wydajność.

W poniższej tabeli wymieniono opcje kompilatora i funkcje języka, które są niezgodne z opcją **/MP** :

|Funkcja opcji lub języka|Opis|
|--------------------------------|-----------------|
|[#import](../../preprocessor/hash-import-directive-cpp.md) dyrektywy preprocesora|Konwertuje typy w bibliotece typów na klasy języka C++, a następnie zapisuje te klasy do pliku nagłówkowego.|
|[/e](e-preprocess-to-stdout.md), [/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Kopiuje dane wyjściowe preprocesora do standardowego wyjścia (**stdout**).|
|[/GM](gm-enable-minimal-rebuild.md)|Przestarzałe. Włącza kompilację przyrostową.|
|[/showIncludes](showincludes-list-include-files.md)|Zapisuje listę plików dołączanych do błędu standardowego (**stderr**).|
|[/YC](yc-create-precompiled-header-file.md)|Zapisuje prekompilowany plik nagłówkowy.|

## <a name="diagnostic-messages"></a>Komunikaty diagnostyczne

Jeśli określisz opcję lub funkcję języka, która jest niezgodna z opcją **/MP** , zostanie wyświetlony komunikat diagnostyczny. Poniższa tabela zawiera listę komunikatów i zachowanie kompilatora:

|Komunikatu diagnostyczny|Opis|Zachowanie kompilatora|
|------------------------|-----------------|-----------------------|
|**C2813**|Dyrektywa **#import** nie jest zgodna z opcją **/MP** .|Kompilacja zostaje zakończona, chyba że opcja [poziomu ostrzeżenia kompilatora](compiler-option-warning-level.md) nie zostanie podaną w przeciwnym razie.|
|**D9014**|Określono nieprawidłową wartość dla argumentu *processMax* .|Kompilator ignoruje nieprawidłową wartość i przyjmuje wartość 1.|
|**D9030**|Określona opcja jest niezgodna z **/MP**.|Kompilator ignoruje opcję **/MP** .|

## <a name="guidelines"></a><a name="guidelines"></a> Wiele

### <a name="measure-performance"></a>Mierzenie wydajności

Użyj łącznego czasu kompilacji do mierzenia wydajności. Można mierzyć czas kompilacji za pomocą zegara fizycznego lub użyć oprogramowania, które oblicza różnicę między rozpoczęciem i zatrzymaniem kompilacji. Jeśli komputer ma wiele procesorów, zegar fizyczny może przynieść dokładniejsze wyniki niż pomiar czasu oprogramowania.

### <a name="effective-processors"></a><a name="effective_processors"></a> Efektywne procesory

Komputer może mieć co najmniej jeden procesor wirtualny, który jest również znany jako *skuteczny procesor*, dla każdego z jego procesorów fizycznych. Każdy procesor fizyczny może mieć jeden lub więcej rdzeni, a jeśli system operacyjny umożliwia wielowątkowość dla rdzenia, każdy rdzeń jest prawdopodobnie dwoma procesorami wirtualnymi.

Na przykład komputer ma jeden skuteczny procesor, jeśli ma jeden procesor fizyczny z jednym rdzeniem, a wielowątkowość jest wyłączona. Z kolei komputer ma osiem skutecznych procesorów, jeśli ma dwa procesory fizyczne, z których każdy ma dwa rdzenie, a wszystkie rdzenie mają włączone wielowątkowość. Oznacza to, że (8 skutecznych procesorów) = (2 procesory fizyczne) x (2 rdzenie na procesor fizyczny) x (2 efektywne procesory na rdzeń z powodu wielowątkowości).

Jeśli pominięto argument *processMax* w opcji **/MP** , kompilator uzyska liczbę skutecznych procesorów z systemu operacyjnego, a następnie tworzy jeden proces na efektywny procesor. Jednak kompilator nie może zagwarantować, który proces jest wykonywany na określonym procesorze; system operacyjny podejmuje tę decyzję.

### <a name="number-of-processes"></a>Liczba procesów

Kompilator oblicza liczbę procesów, które zostaną użyte do skompilowania plików źródłowych. Ta wartość jest mniejszą liczbą plików źródłowych, która została określona w wierszu polecenia, oraz liczbę procesów jawnie lub niejawnie określanych przy użyciu opcji **/MP** . Można jawnie ustawić maksymalną liczbę procesów w przypadku podania argumentu *processMax* opcji **/MP** . Można też użyć wartości domyślnej, która jest równa liczbie efektywnych procesorów w komputerze, jeśli pominięto argument *processMax* .

Załóżmy na przykład, że określisz następujący wiersz polecenia:

`cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`

W takim przypadku kompilator używa pięciu procesów, ponieważ jest to mniej z pięciu plików źródłowych i maksymalnie siedem procesów. Alternatywnie Załóżmy, że komputer ma dwa efektywne procesory i należy określić następujący wiersz polecenia:

`cl /MP a.cpp b.cpp c.cpp`

W takim przypadku system operacyjny zgłasza dwa procesory; w związku z tym kompilator używa dwóch procesów w obliczeniach. W związku z tym kompilator wykona kompilację z dwoma procesami, ponieważ są to dwa procesy i trzy pliki źródłowe.

### <a name="source-files-and-build-order"></a>Pliki źródłowe i kolejność kompilacji

Pliki źródłowe mogą nie być kompilowane w tej samej kolejności, w jakiej występują w wierszu polecenia. Chociaż kompilator tworzy zestaw procesów, które zawierają kopie kompilatora, system operacyjny jest harmonogramem, gdy każdy proces jest wykonywany. W związku z tym nie można zagwarantować, że pliki źródłowe zostaną skompilowane w określonej kolejności.

Plik źródłowy jest kompilowany, gdy proces jest dostępny do skompilowania. Jeśli istnieje więcej plików niż procesy, pierwszy zestaw plików jest kompilowany przez dostępne procesy. Pozostałe pliki są przetwarzane, gdy proces kończy obsługę poprzedniego pliku i jest dostępny do pracy na jednym z pozostałych plików.

Nie określaj tego samego pliku źródłowego wielokrotnie w wierszu polecenia. Taka sytuacja może wystąpić, jeśli na przykład narzędzie automatycznie tworzy plik [reguł programu make](contents-of-a-makefile.md) na podstawie informacji o zależnościach w projekcie. Jeśli nie określisz opcji **/MP** , kompilator przetwarza listę plików sekwencyjnie i ponownie kompiluje każde wystąpienie pliku. Jeśli jednak określisz opcję **/MP** , różne kompilatory mogą kompilować ten sam plik w tym samym czasie. W związku z tym różne kompilatory będą próbować zapisywać w tym samym pliku wyjściowym w tym samym czasie. Jeden kompilator uzyska wyłączny dostęp do zapisu do pliku wyjściowego i zakończy się pomyślnie, a pozostałe kompilatory zakończą się niepowodzeniem z powodu błędu dostępu do pliku.

### <a name="using-type-libraries-import"></a>Korzystanie z bibliotek typów (#import)

Kompilator nie obsługuje stosowania dyrektywy [#import](../../preprocessor/hash-import-directive-cpp.md) z przełącznikiem **/MP** . Jeśli to możliwe, wykonaj następujące kroki, aby obejść ten problem:

- Przenieś wszystkie `#import` dyrektywy w różnych plikach źródłowych do jednego lub kilku plików, a następnie Skompiluj te pliki bez opcji **/MP** . Wynik jest zestawem wygenerowanych plików nagłówkowych.

- W pozostałych plikach źródłowych Wstaw dyrektywy [#include](../../preprocessor/hash-include-directive-c-cpp.md) , które określają wygenerowane nagłówki, a następnie Kompiluj pozostałe pliki źródłowe przy użyciu opcji **/MP** .

### <a name="visual-studio-project-settings"></a>Ustawienia projektu programu Visual Studio

#### <a name="the-msbuildexe-tool"></a>Narzędzie MSBUILD.exe

Program Visual Studio używa narzędzia [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) do kompilowania rozwiązań i projektów. Opcja wiersza polecenia **/maxcpucount:**_Number_ (lub **/m:**_Number_) narzędzia MSBuild.exe może jednocześnie kompilować wiele projektów. I opcja kompilatora **/MP** może jednocześnie kompilować wiele jednostek kompilacji. Jeśli jest to odpowiednie dla aplikacji, Popraw czas kompilacji rozwiązania, używając jednego lub obu typów **/MP** i **/maxcpucount**.

Czas kompilacji w rozwiązaniu częściowo zależy od liczby procesów, które wykonują kompilację. Argument *Number* opcji MSBuild [/maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) określa maksymalną liczbę projektów do skompilowania w tym samym czasie. Analogicznie, argument *processMax* opcji kompilatora **/MP** określa maksymalną liczbę jednostek kompilacji do kompilacji w tym samym czasie. Jeśli opcja **/maxcpucount** określa projekty *P* i opcja **/MP** określa procesy języka *C* , w tym samym czasie wykonuje się maksymalnie *P* x *C* procesów.

Wskazówki dotyczące decydowania o korzystaniu z technologii MSBuild lub **/MP** są następujące:

- Jeśli istnieje wiele projektów z kilkoma plikami w każdym projekcie, użyj narzędzia MSBuild.

- Jeśli w każdym projekcie istnieje kilka projektów z wieloma plikami, użyj opcji **/MP** .

- Jeśli liczba projektów i plików na projekt jest zrównoważona, należy użyć programu MSBuild i **/MP**. Początkowo ustaw opcję **/maxcpucount** na liczbę projektów do skompilowania i opcję **/MP** dla liczby procesorów na komputerze. Zmierz wydajność, a następnie dostosuj ustawienia, aby uzyskać najlepsze wyniki. Powtarzaj ten cykl do momentu, aż zostanie osiągnięty całkowity czas kompilacji.

## <a name="see-also"></a>Zobacz też

[#import — dyrektywa](../../preprocessor/hash-import-directive-cpp.md)<br/>
[Dokumentacja wiersza polecenia](/visualstudio/msbuild/msbuild-command-line-reference)<br/>
[/Zf (Szybsze generowanie pliku PDB)](zf.md)<br/>
