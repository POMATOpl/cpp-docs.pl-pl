---
description: Dowiedz się więcej na temat:/sterownika trybu jądra systemu Windows NT
title: /DRIVER (Sterownik trybu jądra Windows NT)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: a9c066aa58b6cae64bd60ab451c6edd04f71f256
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201095"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Sterownik trybu jądra Windows NT)

>/[: TYLKO DO-DO |: WDM]

## <a name="remarks"></a>Uwagi

Aby skompilować sterownik trybu jądra systemu Windows NT, użyj opcji **/konsolidatora** .

/Sterownika **: tylko** powoduje, że konsolidator dodaje **IMAGE_FILE_UP_SYSTEM_ONLY** bit do charakterystyki w nagłówku danych wyjściowych, aby określić, że jest to sterownik jednoprocesorowy. System operacyjny odmówi załadowania sterownika w systemie wieloprocesorowym (MP).

/Via **: WDM** powoduje, że konsolidator ustawia **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** bit w polu DLLCHARACTERISTICS nagłówka opcjonalnego.

Jeśli **nie** zostanie określony, te bity nie są ustawiane przez konsolidator.

Jeśli **jest** określony:

- **/FIXED: nie** obowiązuje. Aby uzyskać więcej informacji, zobacz [/FIXED (stały adres podstawowy)](fixed-fixed-base-address.md).

- Rozszerzenie pliku wyjściowego jest ustawione na. sys. Użyj **/out** , aby zmienić domyślną nazwę pliku i rozszerzenie. Aby uzyskać więcej informacji, zobacz [/out (nazwa pliku wyjściowego)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **systemu** .

1. Zmodyfikuj właściwość **sterownika** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz [Właściwość cvlinkertool. Driver](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver).

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
