---
description: Dowiedz się więcej na temat:/VERSION (informacje o wersji)
title: /VERSION (Informacje o wersji)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 7c6a27e4829c4acf66db2887e01a147aceb1c5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176369"
---
# <a name="version-version-information"></a>/VERSION (Informacje o wersji)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Argumenty

*Główne* i *pomocnicze*<br/>
Żądany numer wersji w nagłówku pliku. exe lub. dll.

## <a name="remarks"></a>Uwagi

Opcja/VERSION nakazuje konsolidatorowi umieszczenie numeru wersji w nagłówku pliku. exe lub. dll. Użyj polecenia DUMPBIN [/Headers](headers.md) , aby wyświetlić pole wersja obrazu opcjonalnych wartości nagłówka, aby zobaczyć efekt/Version.

Argumenty *Główne* i *pomocnicze* są liczbami dziesiętnymi z zakresu od 0 do 65 535. Wartość domyślna to 0,0.

Informacje podane w pliku/VERSION nie mają wpływu na informacje o wersji, które pojawiają się dla aplikacji podczas przeglądania jej właściwości w Eksploratorze plików. Informacje o tej wersji pochodzą z pliku zasobów, który jest używany do kompilowania aplikacji. Aby uzyskać więcej informacji, zobacz [Edytor informacji o wersji](../../windows/version-information-editor.md) .

Innym sposobem wstawienia numeru wersji jest instrukcja [Version](version-c-cpp.md) -Definition.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Ogólne** .

1. Zmodyfikuj właściwość **Version** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
