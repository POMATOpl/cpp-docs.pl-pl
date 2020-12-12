---
description: Dowiedz się więcej o:/FIXED (stały adres podstawowy)
title: /FIXED (Stałe adresy podstawowe)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: 08b781b7fbeaf43d6c7e0e82da7bf8319cf77953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192060"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Stałe adresy podstawowe)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Uwagi

Nakazuje systemowi operacyjnemu załadowanie programu wyłącznie na swój preferowany adres podstawowy. Jeśli preferowany adres podstawowy jest niedostępny, system operacyjny nie ładuje pliku. Aby uzyskać więcej informacji, zobacz [/Base (adres podstawowy)](base-base-address.md).

/FIXED: nie jest domyślnym ustawieniem dla biblioteki DLL, a/FIXED jest domyślnym ustawieniem dla każdego innego typu projektu.

Jeśli/FIXED jest określony, LINK nie generuje sekcji relokacji w programie. W czasie wykonywania, jeśli system operacyjny nie może załadować programu pod określonym adresem, generuje komunikat o błędzie i nie ładuje programu.

Określ/FIXED: nie, aby wygenerować sekcję relokacji w programie.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Wpisz nazwę i ustawienie opcji w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
