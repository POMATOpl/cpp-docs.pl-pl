---
title: Dziedziczenie właściwości w projektach programu Visual Studio — C++
description: Jak dziedziczenie właściwości działa w natywnym (MSBuild) projektach Visual Studio C++.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 17b23426f70bb2d306491e538d30cffc0f202362
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919218"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Dziedziczenie właściwości w projektach programu Visual Studio

Natywny system projektu programu Visual Studio jest oparty na programie MSBuild. Program MSBuild definiuje formaty plików i reguły do tworzenia projektów dowolnego rodzaju. Zarządza większością złożoności kompilowania dla wielu konfiguracji i platform. Warto zrozumieć, jak to działa. Jest to szczególnie ważne, jeśli chcesz zdefiniować konfiguracje niestandardowe. Lub, aby utworzyć zestawy właściwości do wielokrotnego użytku, które można udostępniać i importować do wielu projektów.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>Plik. vcxproj,. props — pliki i. targets

::: moniker range="msvc-140"

Właściwości projektu są przechowywane w kilku plikach. Niektóre są przechowywane bezpośrednio w *`.vcxproj`* pliku projektu. Inne pochodzą z innych *`.targets`* lub *`.props`* plików, które są importowane przez plik projektu i które dostarczają wartości domyślne. Pliki projektu programu Visual Studio 2015 są dostępne w folderze specyficznym dla ustawień regionalnych w katalogu podstawowym *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\v140`* .

::: moniker-end

::: moniker range="msvc-150"

Właściwości projektu są przechowywane w kilku plikach. Niektóre są przechowywane bezpośrednio w *`.vcxproj`* pliku projektu. Inne pochodzą z innych *`.targets`* lub *`.props`* plików, które są importowane przez plik projektu i które dostarczają wartości domyślne. Pliki projektu programu Visual Studio 2017 są dostępne w folderze specyficznym dla ustawień regionalnych w katalogu podstawowym *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* .

::: moniker-end

::: moniker range=">=msvc-160"

Właściwości projektu są przechowywane w kilku plikach. Niektóre są przechowywane bezpośrednio w *`.vcxproj`* pliku projektu. Inne pochodzą z innych *`.targets`* lub *`.props`* plików, które są importowane przez plik projektu i które dostarczają wartości domyślne. Pliki projektu programu Visual Studio znajdują się w folderze, który jest specyficzny dla ustawień regionalnych, w katalogu podstawowym *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>`* . `<version>`Jest on specyficzny dla wersji programu Visual Studio. Jest to *`v160`* program Visual Studio 2019.

::: moniker-end

Właściwości są również przechowywane w plikach niestandardowych *`.props`* , które można dodać do własnego projektu. Zdecydowanie zalecamy, aby *nie* edytować tych plików ręcznie. Zamiast tego należy użyć stron właściwości w IDE, aby zmodyfikować wszystkie właściwości, szczególnie te, które uczestniczą w dziedziczeniu, chyba że masz głębokie zrozumienie programu MSBuild i *`.vcxproj`* plików.

Jak pokazano wcześniej, taka sama właściwość dla tej samej konfiguracji może mieć przypisaną inną wartość w tych różnych plikach. Podczas kompilowania projektu aparat MSBuild ocenia plik projektu i wszystkie zaimportowane pliki w dobrze zdefiniowanej kolejności opisanej później. W miarę oceniania każdego pliku wszystkie wartości właściwości zdefiniowane w tym pliku zastąpią istniejące wartości. Wszystkie wartości, które nie są określone, są dziedziczone z plików, które zostały ocenione wcześniej. Podczas ustawiania właściwości przy użyciu stron właściwości należy również zwrócić uwagę na to, gdzie ją ustawisz. Jeśli ustawisz właściwość na "X" w *`.props`* pliku, ale właściwość jest ustawiona na "t" w pliku projektu, projekt zostanie skompilowany z właściwością ustawioną na wartość "y". Jeśli ta sama właściwość jest ustawiona na wartość "Z" w elemencie projektu, takim jak *`.cpp`* plik, aparat MSBuild będzie używać wartości "z".

Oto podstawowe drzewo dziedziczenia:

1. Ustawienia domyślne z zestawu narzędzi programu MSBuild CPP ( *`Microsoft.Cpp.Default.props`* plik w katalogu podstawowym, który jest importowany przez *`.vcxproj`* plik).

1. Arkusze właściwości

1. *`.vcxproj`* rozszerzeniem. (Ten plik może zastąpić domyślne ustawienia arkusza właściwości.)

1. Metadane elementów

> [!TIP]
> Na stronie właściwości Właściwość **pogrubiona** jest definiowana w bieżącym kontekście. Właściwość czcionką normalną jest dziedziczona.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Wyświetlanie rozwiniętego pliku projektu ze wszystkimi zaimportowanymi wartościami

Czasami warto wyświetlić plik rozszerzony w celu stwierdzenia, jak jest dziedziczona dana wartość właściwości. Aby wyświetlić rozszerzoną wersję, wprowadź następujące polecenie w wierszu polecenia Visual Studio. (Zastąp nazwy plików zastępczych nazwami, których chcesz używać.)

> **MSBuild/PP:**_temp_**. txt** _MojaApl_**. vcxproj**

Rozwinięte pliki projektu mogą być duże i trudne do zrozumienia, chyba że znasz program MSBuild. Oto podstawowa struktura pliku projektu:

1. Podstawowe właściwości projektu, które nie są ujawniane w środowisku IDE.

1. Import *`Microsoft.cpp.default.props`* , który definiuje niektóre podstawowe właściwości niezależne od zestawu narzędzi.

1. Globalne właściwości konfiguracji (uwidocznione jako **PlatformToolset** i domyślne właściwości **projektu** na stronie **Ogólne konfiguracji** ). Te właściwości określają, który zestaw narzędzi i wewnętrzne arkusze właściwości są importowane w *`Microsoft.cpp.props`* następnym kroku.

1. Import *`Microsoft.cpp.props`* , który ustawia większość wartości domyślnych projektu.

1. Importuj wszystkie arkusze właściwości, w tym *`.user`* pliki. Te arkusze właściwości mogą zastąpić wszystko, z wyjątkiem właściwości domyślnych **PlatformToolset** i **Project** .

1. Pozostałe właściwości konfiguracji projektu. Te wartości mogą zastąpić to, co ustawiono w arkuszach właściwości.

1. Elementy (pliki) wraz z ich metadanymi. Te elementy są zawsze ostatnim słowem w regułach oceny MSBuild, nawet jeśli występują przed innymi właściwościami i importami.

Aby uzyskać więcej informacji, zobacz [Właściwości programu MSBuild](/visualstudio/msbuild/msbuild-properties).

## <a name="build-configurations"></a>Konfiguracje kompilacji

Konfiguracja jest tylko dowolną grupą właściwości, które mają nazwę. Program Visual Studio oferuje konfiguracje debugowania i wydawania. Każda z nich ustawia różne właściwości odpowiednio dla kompilacji debugowania lub kompilacji wydania. Za pomocą **Configuration Manager** można definiować konfiguracje niestandardowe. Są one wygodnym sposobem grupowania właściwości dla określonej wersji kompilacji.

Aby lepiej poznać konfiguracje kompilacji, Otwórz **Menedżer właściwości** . Można go otworzyć, wybierając pozycję **wyświetl > Menedżer właściwości** lub **widok > innych Menedżer właściwości > systemu Windows** , w zależności od ustawień. **Menedżer właściwości** ma węzły dla każdej pary konfiguracji i platformy w projekcie. W każdym z tych węzłów są węzły dla arkuszy właściwości ( *`.props`* pliki), które ustawiają określone właściwości dla danej konfiguracji.

![Menedżer właściwości](media/property-manager.png "Menedżer właściwości")

Na przykład możesz przejść do okienka ogólne na stronach właściwości. Zmień wartość właściwości zestaw znaków na "nie ustawiono" zamiast "Użyj Unicode", a następnie kliknij przycisk **OK** . Menedżer właściwości teraz nie zawiera arkusza właściwości **obsługi Unicode** . Jest ona usuwana dla bieżącej konfiguracji, ale nadal istnieje inna konfiguracja.

Aby uzyskać więcej informacji na temat Menedżer właściwości i arkuszy właściwości, zobacz [udostępnianie lub ponowne używanie ustawień projektu programu Visual Studio C++](create-reusable-property-configurations.md).

> [!TIP]
> *`.user`* Plik jest starszą funkcją. Firma Microsoft zaleca, aby je usunąć, aby zachować właściwości prawidłowo pogrupowane zgodnie z konfiguracją i platformą.
