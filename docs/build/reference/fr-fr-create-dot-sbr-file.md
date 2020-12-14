---
description: Dowiedz się więcej na temat:/FR,/fr (Create. Plik SBR)
title: /FR, /Fr (Utwórz plik .Sbr)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
ms.openlocfilehash: 9142e7afedb55a7b0f4ed0cdb56e4288524d7afc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200419"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (Utwórz plik .Sbr)

Tworzy pliki. sbr.

## <a name="syntax"></a>Składnia

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Uwagi

> [!WARNING]
> Mimo że usługa BSCMAKE jest nadal zainstalowana z programem Visual Studio, nie jest już używana przez IDE. Od programu Visual Studio 2008 informacje dotyczące przeglądania i symboli są przechowywane automatycznie w pliku SQL Server. sdf w folderze rozwiązania.

W trakcie procesu kompilacji narzędzie do konserwacji plików z informacjami w witrynie Microsoft Browse (BSCMAKE) używa tych plików do utworzenia. Plik BSC, który służy do wyświetlania informacji o przeglądaniu.

**/Fr** tworzy plik. sbr z pełnymi informacjami symbolicznymi.

**/Fr** tworzy plik. sbr bez informacji o zmiennych lokalnych.

Jeśli nie określisz `filename` , plik. sbr pobiera taką samą nazwę bazową jak plik źródłowy.

**/Fr** jest przestarzała; Zamiast tego użyj **/fr** . Aby uzyskać więcej informacji, zobacz Opcje kompilatora przestarzałe i usunięte w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

> [!NOTE]
> Nie należy zmieniać rozszerzenia. sbr. BSCMAKE wymaga, aby pliki pośredniczące miały takie rozszerzenie.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. W okienku nawigacji wybierz stronę właściwości **C/C++**, **Przeglądaj informacje** .

1. Zmodyfikuj **plik informacji o przeglądaniu** lub **Włącz Właściwość przeglądania informacji** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A> .

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Określanie nazwy ścieżki](specifying-the-pathname.md)
