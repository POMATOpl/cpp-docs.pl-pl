---
description: Dowiedz się więcej o:/STUB (nazwa pliku szczątkowego systemu MS-DOS)
title: /STUB (Nazwa pliku klasy zastępczej MS-DOS)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 34f3cd71ce66cb6695a58707fd84de79f7a14b1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230305"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (Nazwa pliku klasy zastępczej MS-DOS)

```
/STUB:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Aplikacja systemu MS-DOS.

## <a name="remarks"></a>Uwagi

Opcja/STUB dołącza do programu Win32 program zastępczy systemu MS-DOS.

Wywoływany jest program zastępczy, jeśli plik jest wykonywany w systemie MS-DOS. Zwykle wyświetla odpowiedni komunikat; jednak każda prawidłowa aplikacja MS-DOS może być programem zastępczym.

Określ *nazwę pliku* dla programu zastępczego po dwukropku (:) w wierszu polecenia. Konsolidator sprawdza *nazwę pliku* i wysyła komunikat o błędzie, jeśli plik nie jest plikiem wykonywalnym. Program musi być plikiem. exe; plik. com jest nieprawidłowy dla programu zastępczego.

Jeśli ta opcja nie jest używana, konsolidator dołącza domyślny program zastępczy, który wystawia następujący komunikat:

```
This program cannot be run in MS-DOS mode.
```

Podczas kompilowania sterownika urządzenia wirtualnego *Nazwa pliku* umożliwia użytkownikowi określenie nazwy pliku zawierającej strukturę IMAGE_DOS_HEADER (zdefiniowaną w programie Winnt. H) do użycia w VXD zamiast domyślnego nagłówka.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
