---
description: Dowiedz się więcej o:/TLBID (Określ identyfikator zasobu dla biblioteki typów)
title: /TLBID (Określ identyfikator ID zasobu dla TypeLib)
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: 4958229cbebe988867c5419d7953b6ffd968e45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230019"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (Określ identyfikator ID zasobu dla TypeLib)

```
/TLBID:id
```

## <a name="arguments"></a>Argumenty

*id*<br/>
Wartość określona przez użytkownika dla biblioteki typów utworzonych przez konsolidator. Zastępuje domyślny identyfikator zasobu 1.

## <a name="remarks"></a>Uwagi

Podczas kompilowania programu, który używa atrybutów, konsolidator utworzy bibliotekę typów. Konsolidator przypisze identyfikator zasobu 1 do biblioteki typów.

Jeśli ten identyfikator zasobu powoduje konflikt z jednym z istniejących zasobów, można określić inny identyfikator z/TLBID. Zakres wartości, do których można przekazać, `id` to od 1 do 65535.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **osadzony IDL** .

1. Zmodyfikuj właściwość **Identyfikator zasobu biblioteki typów** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
