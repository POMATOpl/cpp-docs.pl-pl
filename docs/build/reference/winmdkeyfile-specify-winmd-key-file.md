---
description: Dowiedz się więcej na temat:/WINMDKEYFILE (Określ plik klucza winmd)
title: /WINMDKEYFILE (określ plik klucza winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 0e7b23de62613f51c3824b107e55180bb54780d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258905"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (określ plik klucza winmd)

Określa klucz lub parę kluczy, aby podpisać plik metadanych środowisko wykonawcze systemu Windows (WinMD).

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Uwagi

Przypomina opcję konsolidatora [/KeyFile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) , która jest stosowana do pliku winmd.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **metadanych systemu Windows** .

1. W polu **plik klucza metadanych systemu Windows** wprowadź lokalizację pliku.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
