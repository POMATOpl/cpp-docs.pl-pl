---
description: 'Dowiedz się więcej na temat: jak ustawiać właściwości analizy kodu dla projektów C/C++'
title: 'Porady: ustawianie właściwości analizy kodu dla projektów C/C++'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.native
- VC.Project.VCCLCompilerTool.EnablePrefast
- VC.Project.VCFxCopTool.EnablePREfast
- VC.Project.VCFxCopTool.IgnoreGeneratedCode
helpviewer_keywords:
- properties, C/C++ Code Analysis
- properties, Code Analysis
- code analysis properties
- C/C++ code analysis properties
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
ms.openlocfilehash: 590254406242c369da9aff91d006313ed797078f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151570"
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>Porady: ustawianie właściwości analizy kodu dla projektów C/C++

Można skonfigurować reguły używane przez narzędzie do analizy kodu do analizowania kodu w każdej konfiguracji projektu. Ponadto można skierować analizę kodu, aby pominąć ostrzeżenia z kodu, który został wygenerowany i dodany do projektu przez narzędzie innej firmy.

## <a name="code-analysis-property-page"></a>Strona właściwości analizy kodu

Strona właściwości **Analiza kodu** zawiera wszystkie ustawienia konfiguracji analizy kodu dla projektu MSBuild. Aby otworzyć stronę właściwości Analiza kodu dla projektu w **Eksplorator rozwiązań**, kliknij prawym przyciskiem myszy projekt, a następnie kliknij polecenie **Właściwości**. Następnie rozwiń węzeł **Właściwości konfiguracji** i wybierz kartę **Analiza kodu** .

## <a name="project-configuration-and-platform"></a>Konfiguracja i platforma projektu

Lista **konfiguracji** i lista **platform** w górnej części okna umożliwiają stosowanie różnych ustawień analizy kodu do różnych konfiguracji projektu i kombinacji platform. Na przykład można skierować analizę kodu w celu zastosowania jednego zestawu reguł do projektu na potrzeby kompilacji debugowania i innego zestawu dla kompilacji wydań.

## <a name="enabling-code-analysis"></a>Włączanie analizy kodu

Możesz włączyć analizę kodu dla projektu, przełączając opcje **Włącz analizę kodu firmy Microsoft** i **Włącz opcję Clang-uporządkowanego** , a następnie skonfiguruj, czy ma on działać w ramach kompilacji, wybierając pozycję **Włącz analizę kodu podczas kompilacji**. W połączeniu z listą **konfiguracji** można na przykład zdecydować, aby wyłączyć analizę kodu dla kompilacji debugowania i włączyć ją dla kompilacji wydań.

Analiza kodu została zaprojektowana w celu ułatwienia poprawy jakości kodu i unikania typowych pułapek. W związku z tym należy uważnie rozważyć, czy należy wyłączyć analizę kodu. Zazwyczaj lepiej jest wyłączyć zestawy reguł, indywidualne reguły lub indywidualne kontrole, które nie mają być stosowane do projektu.

## <a name="cmake-configuration"></a>Konfiguracja CMake

W projektach CMake Zmień wartość `enableMicrosoftCodeAnalysis` `enableClangTidyCodeAnalysis` kluczy i w programie, `CMakeSettings.json` Aby włączyć lub wyłączyć analizę kodu. Aby uzyskać więcej informacji, zobacz [używanie Clang-Tidy w programie Visual Studio](../code-quality/clang-tidy.md) .

## <a name="see-also"></a>Zobacz też

- [Analiza jakości zarządzanego kodu](/visualstudio/code-quality/code-analysis-for-managed-code-overview)
- [Analiza kodu dla ostrzeżeń C/C++](../code-quality/code-analysis-for-c-cpp-warnings.md)
- [Użyj zestawów reguł, aby określić reguły języka C++ do uruchomienia](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [Korzystanie z Clang-uporządkowanego](../code-quality/clang-tidy.md)
