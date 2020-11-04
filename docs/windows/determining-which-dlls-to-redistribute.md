---
title: Ustalanie, które biblioteki DLL są przeznaczone do ponownej dystrybucji
ms.date: 07/15/2019
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
ms.openlocfilehash: 079bfa33ced9f62d6abbccca86435b1b5654a2de
ms.sourcegitcommit: d77159732a8e782b2a1b7abea552065f2b6f61c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2020
ms.locfileid: "93344712"
---
# <a name="determining-which-dlls-to-redistribute"></a>Ustalanie, które biblioteki DLL są przeznaczone do ponownej dystrybucji

Podczas kompilowania aplikacji korzystającej z bibliotek DLL dostarczonych przez program Visual Studio użytkownicy aplikacji muszą także mieć te biblioteki dll na swoich komputerach, aby można było uruchomić aplikację. Ponieważ większość użytkowników prawdopodobnie nie ma zainstalowanego programu Visual Studio, należy podać te biblioteki DLL. Program Visual Studio udostępnia te biblioteki DLL jako *pliki redystrybucyjne* , które można dołączać do Instalatora aplikacji.

Aby ułatwić uwzględnienie bibliotek DLL redystrybucyjnych w instalatorze, są one dostępne jako autonomiczne *pakiety redystrybucyjne*. Są to pliki wykonywalne specyficzne dla architektury, które używają wdrożenia centralnego do instalowania plików redystrybucyjnych na komputerze użytkownika. Na przykład VCRedist \_x86.exe instaluje biblioteki 32-bitowe dla komputerów z procesorami x86 i x64, vcredist \_x64.exe instaluje biblioteki 64-bitowe dla komputerów x64, a VCRedist \_ARM.exe instaluje biblioteki dla komputerów ARM. Zalecamy centralne wdrożenie, ponieważ firma Microsoft może używać usługi Windows Update do niezależnego aktualizowania tych bibliotek. Oprócz kopii w instalacji programu Visual Studio, bieżące pakiety redystrybucyjne są dostępne do pobrania. Aby uzyskać linki do najnowszych obsługiwanych pakietów redystrybucyjnych dla bieżących i starszych zestawów narzędzi, zobacz [najnowsze obsługiwane Visual C++ pliki do pobrania](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads). Określone wcześniejsze wersje pakietów redystrybucyjnych można znaleźć, przeszukując [Centrum pobierania Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=158431) "Visual C++ pakiety redystrybucyjne".

Główny numer wersji wdrażanego pakietu redystrybucyjnego musi być zgodny z wersją zestawu narzędzi programu Visual Studio używanego do tworzenia aplikacji, a wersja pomocnicza musi być taka sama lub wyższa. Program Visual Studio 2017 i Visual Studio 2015 mają zgodne numery wersji zestawu narzędzi, co oznacza, że pliki redystrybucyjne programu Visual Studio 2017 mogą być używane przez aplikacje skompilowane przy użyciu zestawu narzędzi systemu 2015. Chociaż mogą one być zgodne, nie obsługujemy używania plików redystrybucyjnych 2015 w aplikacjach skompilowanych przy użyciu zestawu narzędzi 2017. Obsługujemy tylko pakiet redystrybucyjny, który jest taki sam jak wersja zestawu narzędzi lub nowszy.

Innym sposobem dołączenia bibliotek DLL redystrybucyjnych do instalatora jest użycie *modułów scalania*. Te moduły Instalatora firmy Microsoft są dołączone do programu i instalowane przez Instalatora aplikacji. Moduły scalania dla bibliotek DLL redystrybucyjnych znajdują się w katalogu instalacyjnym programu Visual Studio w obszarze \\ VC \\ Redist\MSVC \\ *Version* \\ MergeModules \\ . We wcześniejszych wersjach programu Visual Studio te pliki znajdują się w katalogu \\ Program Files lub \\ Program Files (x86) we wspólnym \\ podkatalogu modułów scalania plików. Aby uzyskać więcej informacji o korzystaniu z tych plików, zobacz [Redystrybuowanie składników za pomocą modułów scalania](redistributing-components-by-using-merge-modules.md).

Poszczególne redystrybucyjne biblioteki DLL są również dołączone do instalacji programu Visual Studio. Domyślnie są one instalowane w katalogu instalacyjnym programu Visual Studio w \\ \\ folderze VC Redist \\ MSVC \\ *Version* . Numery *wersji* mogą reprezentować różne pomocnicze numery kompilacji pojedynczego wspólnego zestawu plików redystrybucyjnych. Użyj najnowszej wersji pliku DLL biblioteki, pakietu redystrybucyjnego lub modułu scalania znalezionego w tych katalogach. Możesz użyć tych bibliotek do wdrożenia lokalnego, instalując je w tym samym katalogu, w którym znajduje się aplikacja. Wdrożenie lokalne nie jest zalecane, ponieważ jest ono odpowiedzialne za dostarczanie aktualizacji wdrożonych aplikacji. Zalecane jest wdrażanie centralne przy użyciu pakietów redystrybucyjnych.

Aby określić, które biblioteki dll mają być rozpowszechniane z aplikacją, Zbierz listę bibliotek DLL, od których zależy aplikacja. Są one zazwyczaj wymienione jako dane wejściowe biblioteki Import do konsolidatora. Niektóre biblioteki, takie jak vcruntime i uniwersalna biblioteka środowiska uruchomieniowego C (UCRT), są domyślnie uwzględniane. Jeśli aplikacja lub jedna z jej zależności używa funkcji LoadLibrary do dynamicznego ładowania biblioteki DLL, Ta biblioteka DLL może nie być wyświetlana w danych wejściowych dla konsolidatora. Jednym ze sposobów zebrania listy dynamicznie ładowanych bibliotek DLL jest uruchomienie analizatora zależności (depends.exe) w aplikacji, zgodnie z opisem w temacie [zależności aplikacji Visual C++](understanding-the-dependencies-of-a-visual-cpp-application.md). Niestety, to narzędzie jest nieaktualne i może zgłosić, że nie można znaleźć niektórych bibliotek DLL.

Jeśli masz listę zależności, porównaj ją z listą połączoną w pliku Redist.txt znajdującym się w katalogu instalacyjnym Microsoft Visual Studio lub z "listą Redist" w odniesieniu do bibliotek DLL, które są przywoływane w sekcji "pliki kodu dystrybucyjnego" postanowień licencyjnych dotyczących oprogramowania firmy Microsoft dla kopii programu Visual Studio. W przypadku programu Visual Studio 2017 zobacz [Kod dystrybucyjny dla Microsoft Visual Studio 2017 (obejmuje narzędzia, rozszerzalność i pliki BuildServer)](/visualstudio/productinfo/2017-redistribution-vs). W przypadku programu Visual Studio 2015 zobacz [Kod dystrybucyjny dla Microsoft Visual Studio 2015 i Microsoft Visual Studio 2015 SDK (obejmuje programy narzędziowe i pliki BuildServer)](/visualstudio/productinfo/2015-redistribution-vs). W przypadku Visual Studio 2013 lista jest dostępna online w [kodzie dystrybucyjnym dla Microsoft Visual Studio 2013 i Microsoft Visual Studio 2013 SDK](/visualstudio/productinfo/2013-redistribution-vs).

W wersjach programu Visual Studio przed Visual Studio 2015 Biblioteka środowiska uruchomieniowego języka C (CRT) została uwzględniona jako redystrybucyjna Biblioteka DLL, w MSVC *Version*. dll. Począwszy od programu Visual Studio 2015, funkcje w CRT zostały refaktoryzacjne do vcruntime i UCRT. UCRT jest teraz składnikiem systemowym w systemie Windows 10 zarządzanym przez Windows Update. Jest ona dostępna we wszystkich systemach operacyjnych Windows 10. Aby wdrożyć aplikację we wcześniejszych systemach operacyjnych, może być konieczne ponowne rozproszenie UCRT. Wczesna wersja UCRT jest dołączana do plików redystrybucyjnych programu Visual Studio, które są instalowane tylko w systemach operacyjnych starszych niż Windows 10 i tylko wtedy, gdy nie jest już zainstalowana żadna wersja programu UCRT. Aby uzyskać instalowalną wersję UCRT dla systemów niskiego poziomu jako pakiet aktualizacji systemu Microsoft, zobacz [środowisko uruchomieniowe uniwersalnego języka C systemu Windows 10](https://www.microsoft.com/download/details.aspx?id=48234) w centrum pobierania Microsoft.

Nie można ponownie dystrybuować wszystkich plików uwzględnionych w programie Visual Studio; można tylko ponownie dystrybuować pliki, które są określone w Redist.txt lub na liście Redist "online". Wersje debugowe aplikacji i różne Visual C++ debugowania DLL nie są redystrybucyjne. Aby uzyskać więcej informacji, zobacz [Wybieranie metody wdrożenia](choosing-a-deployment-method.md).

W poniższej tabeli opisano niektóre z Visual C++ bibliotek DLL, od których zależy aplikacja.

|Biblioteka Visual C++|Opis|Dotyczy|
|--------------------------|-----------------|----------------|
|vcruntime *wersja*. dll|Biblioteka środowiska uruchomieniowego dla kodu natywnego.|Aplikacje korzystające z normalnych usług uruchamiania i kończenia języka C i C++.|
|vccorlib *wersja*. dll|Biblioteka środowiska uruchomieniowego dla kodu zarządzanego.|Aplikacje korzystające z usług języka C++ dla kodu zarządzanego.|
|msvcp *wersja*. dll i msvcp w *wersji* _ *dotnumber*. dll|Standardowa biblioteka języka C++ dla kodu natywnego.|Aplikacje korzystające z [standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md).|
|ConcRT *wersja*. dll|Biblioteka środowisko uruchomieniowe współbieżności dla kodu natywnego.|Aplikacje korzystające z [środowisko uruchomieniowe współbieżności](../parallel/concrt/concurrency-runtime.md).|
|MFC *wersja*. dll|Biblioteka Microsoft Foundation Classes (MFC).|Aplikacje korzystające z [biblioteki MFC](../mfc/mfc-desktop-applications.md).|
|Biblioteka MFC w *wersji* *językowej*|Zasoby biblioteki Microsoft Foundation Classes (MFC).|Aplikacje korzystające z określonych zasobów języka dla MFC.|
|*wersja* MFCu.dll|Biblioteka MFC z obsługą standardu Unicode.|Aplikacje korzystające z [biblioteki MFC](../mfc/mfc-desktop-applications.md) i wymagające obsługi standardu Unicode.|
|mfcmifc80.dll|Biblioteka interfejsów zarządzanych przez MFC.|Aplikacje korzystające z [biblioteki MFC](../mfc/mfc-desktop-applications.md) z [kontrolkami Windows Forms](/dotnet/framework/winforms/controls/index).|
|mfcm *wersja*. dll|Biblioteka zarządzana MFC.|Aplikacje korzystające z [biblioteki MFC](../mfc/mfc-desktop-applications.md) z [kontrolkami Windows Forms](/dotnet/framework/winforms/controls/index).|
|*wersja* mfcmu.dll|Biblioteka zarządzana MFC z obsługą standardu Unicode.|Aplikacje korzystające z [biblioteki MFC](../mfc/mfc-desktop-applications.md) z [kontrolkami Windows Forms](/dotnet/framework/winforms/controls/index) i wymagające obsługi standardu Unicode.|
|vcamp *wersja*. dll|Biblioteka AMP dla kodu natywnego.|Aplikacje korzystające z kodu [biblioteki C++ amp](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) .|
|VCOMP *wersja*. dll|Biblioteka OpenMP dla kodu natywnego.|Aplikacje korzystające z kodu [biblioteki OpenMP języka C++](../parallel/openmp/openmp-in-visual-cpp.md) .|

> [!NOTE]
> Nie trzeba już ponownie rozpowszechniać Active Template Library jako oddzielnej biblioteki DLL. Jego funkcjonalność została przeniesiona do nagłówków i biblioteki statycznej.

Aby uzyskać więcej informacji na temat sposobu rozpowszechniania tych bibliotek DLL z aplikacją, zobacz [Redystrybuowanie plików Visual C++](redistributing-visual-cpp-files.md). Aby zapoznać się z przykładami, zobacz [Przykłady wdrożeń](deployment-examples.md).

Zazwyczaj nie trzeba redystrybuować systemowych bibliotek DLL, ponieważ są one częścią systemu operacyjnego. Mogą jednak wystąpić wyjątki, na przykład wtedy, gdy aplikacja będzie działać w kilku wersjach systemów operacyjnych firmy Microsoft. W takim przypadku należy przeczytać odpowiednie postanowienia licencyjne. Ponadto spróbuj uzyskać uaktualnione systemowe biblioteki DLL za pośrednictwem Windows Update, dodatki Service Pack lub pakiety redystrybucyjne udostępnione przez firmę Microsoft.

## <a name="see-also"></a>Zobacz też

[Wybieranie metody wdrażania](choosing-a-deployment-method.md)<br/>
[Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)
