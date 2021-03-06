---
description: 'Dowiedz się więcej o: Strona właściwości zasobów'
title: Zasoby
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d074cbb6035bd138ca322197e50e9a3f892b325b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225105"
---
# <a name="resources-property-page"></a>Strona właściwości zasobów

W przypadku natywnych programów klasycznych systemu Windows kompilacja wywołuje [kompilator zasobów (rc.exe)](/windows/win32/menurc/resource-compiler) do dodawania obrazów, tabel ciągów i plików *. res* do pliku binarnego. Właściwości uwidocznione na tej stronie właściwości są przesyłane do kompilatora zasobów, a nie do kompilatora C++ lub konsolidatora. Aby uzyskać więcej informacji o właściwościach wymienionych w tym miejscu i sposobach mapowania do wersji RC opcji wiersza polecenia, zobacz [using RC (wiersz polecenia RC)](/windows/win32/menurc/using-rc-the-rc-command-line-). Aby uzyskać informacje na temat uzyskiwania dostępu do stron właściwości **zasobów** , zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md). Aby programowo uzyskać dostęp do tych właściwości, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool> .

Właściwości zasobów platformy .NET w aplikacjach C++/CLI są ujawniane na [stronie właściwości zasoby zarządzane](managed-resources-property-page.md).

## <a name="preprocessor-definitions"></a>Definicje preprocesora

Określa co najmniej jedną definicję dla kompilatora zasobów. (/d [makro])

## <a name="undefine-preprocessor-definitions"></a>Usuń Definicje preprocesora

Usuń definicję symbolu. Określ

## <a name="culture"></a>Kultura

Wyświetla listę kultur (na przykład angielski lub włoski) używanych w zasobach. (/l [NUM])

## <a name="additional-include-directories"></a>Dodatkowe katalogi dołączane

Określa co najmniej jeden katalog do dodania do ścieżki dołączania; Użyj ogranicznika średnika, jeśli jest więcej niż jeden. (/I [ścieżka])

## <a name="ignore-standard-include-paths"></a>Ignoruj standardowe ścieżki dołączania

Uniemożliwia kompilatorowi zasobów wyszukiwanie plików dołączanych w katalogach określonych w zmiennych środowiskowych INCLUDE. /X

## <a name="show-progress"></a>Pokaż postęp

Wysyłaj komunikaty o postępie do okna danych wyjściowych. przełącznika

## <a name="suppress-startup-banner"></a>Pomiń transparent startowy

Pomijaj wyświetlanie banera startowego i komunikatu informacyjnego (/nologo)

## <a name="resource-file-name"></a>Nazwa pliku zasobu

Określa nazwę pliku zasobu (/fo [plik])

## <a name="null-terminate-strings"></a>Ciągi kończące wartości null

Dołącz wartość null do wszystkich ciągów w tabelach ciągów. /n

## <a name="see-also"></a>Zobacz też

[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)
