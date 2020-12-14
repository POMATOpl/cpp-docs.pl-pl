---
description: Dowiedz się więcej o:/WINMDFILE (Określ plik WinMD)
title: /WINMDFILE (określ plik winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: fd10768c494bbedfbe650e0f0e3e72e8a062cdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259022"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (określ plik winmd)

Określa nazwę pliku wyjściowego środowisko wykonawcze systemu Windows metadanych (WinMD), który jest generowany przez opcję konsolidatora [/winmd](winmd-generate-windows-metadata.md) .

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Uwagi

Użyj wartości określonej w w programie, `filename` Aby zastąpić domyślną nazwę pliku winmd ( `binaryname` . winmd). Zwróć uwagę, że nie dołączysz "winmd" do `filename` .  Jeśli w wierszu polecenia **/WINMDFILE** zostanie wyświetlona wiele wartości, pierwszeństwo ma Ostatnia.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **metadanych systemu Windows** .

1. W polu **plik metadanych systemu Windows** wprowadź lokalizację pliku.

## <a name="see-also"></a>Zobacz też

[/WINMD (Generuj metadane systemu Windows)](winmd-generate-windows-metadata.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
