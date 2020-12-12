---
description: Dowiedz się więcej na temat:/MANIFEST (Tworzenie manifestu zestawu równoczesnego)
title: /MANIFEST (Tworzenie manifestu dla aplikacji wykonywanych jednocześnie)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
ms.openlocfilehash: 6ab5dd0c0ae04a6ac5377c1c9ee0015f8c64ad54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190708"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Tworzenie manifestu dla aplikacji wykonywanych jednocześnie)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Uwagi

/MANIFEST określa, że konsolidator powinien utworzyć plik manifestu obok siebie. Aby uzyskać więcej informacji na temat plików manifestu, zobacz [Dokumentacja plików manifestu](/windows/win32/SbsCs/manifest-files-reference).

Wartość domyślna to/MANIFEST.

Opcja/MANIFEST: EMBED określa, że konsolidator powinien osadzić plik manifestu w obrazie jako zasób typu RT_MANIFEST. Opcjonalny `ID` parametr jest identyfikatorem zasobu, który ma być używany dla manifestu. Użyj wartości 1 dla pliku wykonywalnego. Użyj wartości 2 dla biblioteki DLL, aby umożliwić jej Określanie zależności prywatnych. Jeśli `ID` parametr nie jest określony, wartość domyślna to 2, jeśli ustawiona jest opcja/dll; w przeciwnym razie wartość domyślna to 1.

Począwszy od programu Visual Studio 2008 pliki manifestu dla plików wykonywalnych zawierają sekcję, która określa informacje o kontroli konta użytkownika (UAC). Jeśli określisz/MANIFEST, ale nie określisz ani [/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md) ani [/dll](dll-build-a-dll.md), domyślny fragment UAC, który ma ustawiony na *jako źródło* poziom kontroli konta użytkownika, zostanie wstawiony do manifestu. Aby uzyskać więcej informacji na temat poziomów kontroli konta użytkownika, zobacz [/MANIFESTUAC (osadza informacje kontroli konta użytkownika w manifeście)](manifestuac-embeds-uac-information-in-manifest.md).

Aby zmienić domyślne zachowanie funkcji Kontrola konta użytkownika, wykonaj jedną z następujących czynności:

- Określ opcję/MANIFESTUAC i ustaw poziom kontroli konta użytkownika na żądaną wartość.

- Lub określ/MANIFESTUAC: NO, jeśli nie chcesz generować fragmentów kontroli konta użytkownika w manifeście.

Jeśli nie określisz/MANIFEST, ale nie określisz komentarzy [/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md) , tworzony jest plik manifestu. Plik manifestu nie jest tworzony w przypadku określenia/MANIFEST: NO.

Jeśli określisz/MANIFEST, nazwa pliku manifestu jest taka sama jak nazwa pliku wyjściowego, ale z. manifest dołączany do nazwy pliku. Na przykład jeśli nazwa pliku wyjściowego jest MyFile.exe, nazwa pliku manifestu to MyFile.exe. manifest.  W przypadku określenia/MANIFESTFILE:*name* Nazwa manifestu jest określana w polu *Nazwa*.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **plik manifestu** .

1. Zmodyfikuj właściwość **Generuj manifest** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
