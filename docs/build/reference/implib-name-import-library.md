---
description: Dowiedz się więcej na temat:/IMPLIB (Nazwij bibliotekę importowaną)
title: /IMPLIB (Nazwij bibliotekę importowaną)
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 2a5ea590368d1bc3abbecf38845e97a99a0d1f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191319"
---
# <a name="implib-name-import-library"></a>/IMPLIB (Nazwij bibliotekę importowaną)

> /IMPLIB:*filename*

## <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Określona przez użytkownika nazwa biblioteki importu. Zastępuje domyślną nazwę.

## <a name="remarks"></a>Uwagi

Opcja/IMPLIB zastępuje domyślną nazwę biblioteki importu, którą tworzy LINK podczas kompilacji programu zawierającego eksporty. Nazwa domyślna jest tworzona na podstawie podstawowej nazwy głównego pliku wyjściowego i rozszerzenia. lib. Program zawiera Eksporty w przypadku określenia co najmniej jednego z następujących elementów:

- Słowo kluczowe [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) w kodzie źródłowym

- Instrukcja [exports](exports.md) w pliku. def

- Specyfikacja [/Export](export-exports-a-function.md) w POleceniu linku

LINK ignoruje/IMPLIB, gdy biblioteka importowa nie jest tworzona. Jeśli nie określono żadnych eksportów, LINK nie tworzy biblioteki importu. Jeśli plik eksportu jest używany w kompilacji, LINK zakłada, że biblioteka importu już istnieje i nie tworzy. Aby uzyskać informacje na temat importowania bibliotek i plików eksportu, zobacz [Dokumentacja biblioteki lib](lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **Import biblioteki** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
