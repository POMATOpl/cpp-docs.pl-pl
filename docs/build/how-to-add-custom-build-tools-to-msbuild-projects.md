---
description: 'Dowiedz się więcej na temat: Instrukcje: Dodawanie niestandardowych narzędzi kompilacji do projektów MSBuild'
title: 'Porady: dodawanie niestandardowych narzędzi kompilacji do projektów MSBuild'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 66ec4a488fd2a089f09ac775d1150300ff662ff2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162823"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Porady: dodawanie niestandardowych narzędzi kompilacji do projektów MSBuild

Niestandardowe narzędzie kompilacji to zdefiniowane przez użytkownika narzędzie wiersza polecenia, które jest skojarzone z określonym plikiem.

Dla określonego pliku Określ w pliku projektu (. vcxproj) wiersz polecenia do wykonania, wszelkie dodatkowe pliki wejściowe lub wyjściowe oraz komunikat do wyświetlenia. Jeśli program **MSBuild** określi, że pliki wyjściowe są nieaktualne w odniesieniu do plików wejściowych, wyświetla komunikat i wykonuje narzędzie wiersza polecenia.

Aby określić, kiedy jest wykonywane narzędzie kompilacji niestandardowej, użyj jednego lub obu `CustomBuildBeforeTargets` `CustomBuildAfterTargets` elementów języka i XML w pliku projektu. Można na przykład określić, że narzędzie kompilacji niestandardowej ma działać po kompilatorze MIDL i przed kompilatorem C/C++. Określ `CustomBuildBeforeTargets` element, który ma zostać wykonany przed uruchomieniem określonego elementu docelowego; `CustomBuildAfterTargets` element, aby wykonać narzędzie po określonym elemencie docelowym, lub oba elementy, aby uruchomić narzędzie między wykonaniem dwóch elementów docelowych. Jeśli żaden element nie zostanie określony, narzędzie kompilacji niestandardowej wykonuje się w lokalizacji domyślnej, która jest przed elementem docelowym **MIDL** .

Niestandardowe kroki kompilacji i niestandardowe narzędzia kompilacji udostępniają informacje określone w `CustomBuildBeforeTargets` `CustomBuildAfterTargets` elementach i XML. Określ te cele jeden raz w pliku projektu.

### <a name="to-add-a-custom-build-tool"></a>Aby dodać niestandardowe narzędzie kompilacji

1. Dodaj grupę elementów do pliku projektu i Dodaj element dla każdego pliku wejściowego. Określ polecenie, dodatkowe dane wejściowe, wyjścia i komunikat jako metadane elementu, jak pokazano poniżej. W tym przykładzie przyjęto założenie, że plik "faq.txt" istnieje w tym samym katalogu, co projekt.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Aby określić, gdzie w kompilacji będą wykonywane narzędzia kompilacji niestandardowej

1. Dodaj następującą grupę właściwości do pliku projektu. Musisz określić co najmniej jeden element docelowy, ale możesz pominąć pozostałe, jeśli chcesz, aby krok kompilacji był wykonywany przed (lub po) określonym elementem docelowym. Ten przykład wykonuje krok niestandardowy po skompilowaniu, ale przed połączeniem.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Zobacz też

[Przewodnik: Tworzenie projektu C++ przy użyciu programu MSBuild](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Instrukcje: korzystanie ze zdarzeń kompilacji w projektach MSBuild](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Instrukcje: Dodawanie niestandardowego kroku kompilacji do projektów MSBuild](how-to-add-a-custom-build-step-to-msbuild-projects.md)
