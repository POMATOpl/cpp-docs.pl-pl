---
description: 'Dowiedz się więcej o: Instrukcje: Dodawanie niestandardowego kroku kompilacji do projektów MSBuild'
title: 'Porady: dodawanie niestandardowego kroku kompilacji do projektów MSBuild'
ms.date: 10/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 1373aa2333fda6e0be9c7c574c5acc7840b9721a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156401"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Porady: dodawanie niestandardowego kroku kompilacji do projektów MSBuild

Niestandardowy krok kompilacji to krok zdefiniowany przez użytkownika w kompilacji. Niestandardowy krok kompilacji zachowuje się jak każdy inny krok *narzędzia poleceń* , taki jak standardowy krok narzędzia do kompilowania lub łączenia.

Określ niestandardowy krok kompilacji w pliku projektu (. vcxproj). Krok może określać wiersz poleceń do wykonania, wszelkie dodatkowe pliki wejściowe lub wyjściowe oraz komunikat do wyświetlenia. Jeśli program **MSBuild** określi, że pliki wyjściowe są nieaktualne w odniesieniu do plików wejściowych, wyświetla komunikat i wykonuje polecenie.

Aby określić lokalizację niestandardowego kroku kompilacji w sekwencji elementów docelowych kompilacji, użyj jednego lub obu `CustomBuildAfterTargets` `CustomBuildBeforeTargets` elementów i elementu XML w pliku projektu. Można na przykład określić, że niestandardowy krok kompilacji będzie uruchamiany po elemencie docelowym narzędzia konsolidacji i przed elementem docelowym narzędzia manifestu. Rzeczywisty zestaw dostępnych elementów docelowych zależy od konkretnej kompilacji.

Określ `CustomBuildBeforeTargets` element, który ma wykonać niestandardowy krok kompilacji przed uruchomieniem określonego elementu docelowego, `CustomBuildAfterTargets` element, który ma wykonać krok po przebiegu określonego elementu docelowego, lub oba elementy, aby wykonać krok między dwoma sąsiednimi obiektami docelowymi. Jeśli żaden z elementów nie zostanie określony, narzędzie kompilacji niestandardowej wykonuje się w lokalizacji domyślnej, która jest po elemencie docelowym **linku** .

Niestandardowe kroki kompilacji i niestandardowe narzędzia kompilacji udostępniają informacje określone w `CustomBuildBeforeTargets` `CustomBuildAfterTargets` elementach i XML. W związku z tym Określ te elementy docelowe tylko raz w pliku projektu.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Aby określić, co jest wykonywane przez krok niestandardowej kompilacji

1. Dodaj grupę właściwości do pliku projektu. W tej grupie Właściwości określ polecenie, jego dane wejściowe i wyjściowe oraz komunikat, jak pokazano w poniższym przykładzie. Ten przykład tworzy plik cab z głównego pliku. cpp utworzonego w [przewodniku: używanie programu MSBuild do tworzenia projektu języka C++](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(ProjectDir)main.cpp</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Aby zdefiniować, gdzie w kompilacji krok kompilacji niestandardowej zostanie wykonany

1. Dodaj następującą grupę właściwości do pliku projektu. Można określić oba elementy docelowe lub można je pominąć, jeśli chcesz, aby krok niestandardowy był wykonywany przed lub po określonym miejscu docelowym. Ten przykład informuje program **MSBuild** , aby wykonał niestandardowy krok po kroku kompilacji, ale przed krokiem linku.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Zobacz też

[Przewodnik: Tworzenie projektu C++ przy użyciu programu MSBuild](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Instrukcje: korzystanie ze zdarzeń kompilacji w projektach MSBuild](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Instrukcje: Dodawanie niestandardowych narzędzi kompilacji do projektów MSBuild](how-to-add-custom-build-tools-to-msbuild-projects.md)
