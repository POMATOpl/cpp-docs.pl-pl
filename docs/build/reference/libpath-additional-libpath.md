---
description: Dowiedz się więcej na temat:/LIBPATH (dodatkowa LIBPATH)
title: /LIBPATH (Dodatkowa Libpath)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: 5db7a0f80cb741a65bac5a4dbb7fd79e28b67459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191033"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Dodatkowa Libpath)

```
/LIBPATH:dir
```

## <a name="parameters"></a>Parametry

*katalogów*<br/>
Określa ścieżkę, która będzie przeszukiwana przez konsolidator przed przeszukaniem ścieżki określonej w opcji środowisko LIB.

## <a name="remarks"></a>Uwagi

Użyj opcji/LIBPATH, aby zastąpić ścieżkę biblioteki środowiska. Konsolidator rozpocznie najpierw wyszukiwanie w ścieżce określonej przez tę opcję, a następnie wyszukanie ścieżki określonej w zmiennej środowiskowej LIB. Dla każdej opcji/LIBPATH można określić tylko jeden katalog. Jeśli chcesz określić więcej niż jeden katalog, musisz określić wiele opcji/LIBPATH. Konsolidator będzie przeszukiwać określone katalogi w kolejności.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Ogólne** .

1. Zmodyfikuj właściwość **Dodatkowe katalogi biblioteki** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
