---
description: Dowiedz się więcej o:/WINMDKEYCONTAINER (Określ kontener kluczy)
title: /WINMDKEYCONTAINER (określ kontener klucza)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 94b203c56b7724c2b2569ba22039da38c4501985
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258996"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (określ kontener klucza)

Określa kontener klucza do podpisania pliku metadanych systemu Windows (WinMD).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Uwagi

Przypomina opcję konsolidatora [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md) , która jest stosowana do pliku (. winmd).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **metadanych systemu Windows** .

1. W polu **kontener klucza metadanych systemu Windows** wprowadź lokalizację.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
