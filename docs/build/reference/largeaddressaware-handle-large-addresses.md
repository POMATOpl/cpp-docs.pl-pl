---
description: Dowiedz się więcej na temat:/LARGEADDRESSAWARE (obsługa dużych adresów)
title: /LARGEADDRESSAWARE (Obsługa dużych adresów)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 72b2ba20b2ea2b91ecd234497c433bcdd9e9ee42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199574"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Obsługa dużych adresów)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>Uwagi

Opcja/LARGEADDRESSAWARE informuje konsolidator, że aplikacja może obsłużyć adresy większe niż 2 gigabajty. W przypadku kompilatorów 64-bitowych ta opcja jest domyślnie włączona. W kompilatorach 32-bitowych/LARGEADDRESSAWARE: nie jest włączone, jeśli/LARGEADDRESSAWARE nie określono inaczej w linii konsolidatora.

Jeśli aplikacja została połączona z/LARGEADDRESSAWARE, polecenia DUMPBIN [/Headers](headers.md) będzie wyświetlała informacje w tym efekcie.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **systemu** .

1. Zmodyfikuj właściwość **enable Large addresss** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
