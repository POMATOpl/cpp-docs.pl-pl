---
title: Używanie Clang-Tidy w programie Visual Studio
description: Jak używać Clang-Tidy w programie Visual Studio do analizy kodu w języku Microsoft C++.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
ms.openlocfilehash: 5b2da222caea435bdb24d774b5e93c995e734bb7
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919075"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Używanie Clang-Tidy w programie Visual Studio

::: moniker range="<=msvc-150"

Obsługa Clang-Tidy wymaga programu Visual Studio 2019 w wersji 16,4 lub nowszej. Aby zapoznać się z dokumentacją tej wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na Visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end

::: moniker range=">=msvc-160"

Analiza kodu natywnie obsługuje [Clang-uporządkowanego](https://clang.llvm.org/extra/clang-tidy/) dla projektów MSBuild i cmake, niezależnie od tego, czy są używane zestawy narzędzi CLANG czy MSVC. Testy Clang-Tidy mogą być uruchamiane w ramach analizy kodu w tle. Pojawiają się one jako ostrzeżenia w edytorze (zygzaki) i są wyświetlane w Lista błędów.

Obsługa Clang-Tidy jest dostępna od wersji 16,4 programu Visual Studio 2019. Jest ona uwzględniana automatycznie po wybraniu obciążenia C++ w Instalator programu Visual Studio.

Clang-Tidy jest domyślnym narzędziem do analizy przy użyciu zestawu narzędzi LLVM/Clang-CL, dostępnego zarówno w programie MSBuild, jak i w CMake. Można ją skonfigurować przy użyciu zestawu narzędzi MSVC do uruchamiania w programie lub do zastępowania standardowego środowiska analizy kodu. Jeśli używasz zestawu narzędzi Clang-CL, analiza kodu firmy Microsoft jest niedostępna.

Clang-Tidy jest uruchamiany po pomyślnej kompilacji. Aby uzyskać Clang-Tidy wyniki, może być konieczne rozwiązanie błędów kodu źródłowego.

## <a name="msbuild"></a>MSBuild

Clang-Tidy można skonfigurować do uruchamiania w ramach analizy kodu i kompilacji na stronie Ogólne **analizy kodu**  >  **General** w okno właściwości projektu. Opcje konfigurowania narzędzia znajdują się w podmenu Clang-Tidy.

Aby uzyskać więcej informacji, zobacz [jak: Ustawianie właściwości analizy kodu dla projektów C/C++](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="cmake"></a>CMake

W projektach CMake można skonfigurować kontrole Clang-Tidy w ramach programu `CMakeSettings.json` . Po otwarciu wybierz pozycję "Edytuj kod JSON" w prawym górnym rogu edytora ustawień projektu CMake. Następujące klucze są rozpoznawane:

- `enableMicrosoftCodeAnalysis`: Włącza analizę kodu firmy Microsoft
- `enableClangTidyCodeAnalysis`: Włącza analizę Clang-Tidy
- `clangTidyChecks`: Clang-Tidy konfiguracja określona jako rozdzielana przecinkami lista, czyli sprawdzenia, czy są włączone lub wyłączone.

Jeśli żadna z opcji "Włącz" nie zostanie określona, program Visual Studio wybierze narzędzie do analizy pasujące do używanego zestawu narzędzi platformy.

## <a name="warning-display"></a>Wyświetlanie ostrzeżeń

Uruchomienia Clang-Tidy powodują wyświetlenie ostrzeżeń w Lista błędów, a jak w edytorze. Użyj kolumny "Kategoria" w Lista błędów, aby sortować i organizować Clang-Tidy ostrzeżeń. Ostrzeżenia w edytorze można skonfigurować przez przełączenie ustawienia "Wyłącz Zawijanie analizy kodu" w obszarze Opcje **narzędzi**  >  **Options** .

## <a name="clang-tidy-configuration"></a>Konfiguracja Clang-Tidy

Można skonfigurować sprawdzanie, czy Clang-uporządkowanego działa w programie Visual Studio za pomocą opcji **checks Clang-uporządkowanego** . Ta wartość wejściowa jest dostarczana z **`--checks`** argumentem narzędzia. Dowolna dodatkowa konfiguracja może być uwzględniona w *`.clang-tidy`* plikach niestandardowych. Aby uzyskać więcej informacji, zobacz [dokumentację Clang-uporządkowanego w witrynie LLVM.org](https://clang.llvm.org/extra/clang-tidy/).

## <a name="see-also"></a>Zobacz także

- [Obsługa Clang/LLVM dla projektów MSBuild](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Obsługa Clang/LLVM dla projektów CMake](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
