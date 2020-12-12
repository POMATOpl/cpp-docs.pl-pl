---
description: Dowiedz się więcej o:/MAP (Generuj Mapfile)
title: /MAP (Generuj plik mapy)
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 28e3823099b4893dcf344a0b1aae99577d850821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176434"
---
# <a name="map-generate-mapfile"></a>/MAP (Generuj plik mapy)

```
/MAP[:filename]
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Określona przez użytkownika nazwa mapfile. Zastępuje domyślną nazwę.

## <a name="remarks"></a>Uwagi

Opcja/MAP informuje konsolidator, aby utworzył mapfile.

Domyślnie konsolidator nazywa mapfile z nazwą podstawową programu i rozszerzeniem. map. Opcjonalna nazwa *pliku* pozwala zastąpić domyślną nazwę mapfile.

Mapfile to plik tekstowy, który zawiera następujące informacje o połączonym programie:

- Nazwa modułu, która jest podstawową nazwą pliku

- Sygnatura czasowa z nagłówka pliku programu (nie z systemu plików)

- Lista grup w programie, z adresem początkowym każdej grupy ( *sekcja*:*przesunięcie*), długość, nazwa grupy i Klasa

- Lista symboli publicznych, z każdym adresem ( *sekcja*:*przesunięcie*), nazwą symbolu, adresem płaskim i plikiem. obj, gdzie symbol jest zdefiniowany

- Punkt wejścia ( *sekcja*:*przesunięcie*)

Opcja [/MapInfo](mapinfo-include-information-in-mapfile.md) określa dodatkowe informacje do uwzględnienia w mapfile.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **debugowania** .

1. Zmodyfikuj właściwość **Generuj plik mapy** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A> .

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
