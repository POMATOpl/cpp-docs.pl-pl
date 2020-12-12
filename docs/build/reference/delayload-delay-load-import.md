---
description: Dowiedz się więcej o:/DELAYLOAD (Opóźnij Importowanie ładowania)
title: /DELAYLOAD (Opóźnij importowanie ładowania)
ms.date: 11/04/2016
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
ms.openlocfilehash: 9f6a91a102b66a16896d51b960d44273a7935d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201498"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Opóźnij importowanie ładowania)

> **/DELAYLOAD:**_nazwa_pliku_dll_

## <a name="parameters"></a>Parametry

*nazwa_pliku_dll*<br/>
Nazwa biblioteki DLL, dla której ma zostać opóźnione ładowanie.

## <a name="remarks"></a>Uwagi

Opcja/DELAYLOAD powoduje załadowanie biblioteki DLL, która jest określona przez, `dllname` do pierwszego wywołania przez program do funkcji w tej bibliotece DLL. Aby uzyskać więcej informacji, zobacz [Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md). Możesz użyć tej opcji tyle razy, ile jest to konieczne, aby określić dowolną liczbę bibliotek DLL. Podczas łączenia programu należy używać delayimp. lib lub można zaimplementować własną funkcję pomocnika ładowania opóźnień.

Opcja [/delay](delay-delay-load-import-settings.md) określa opcje powiązania i ładowania dla każdej biblioteki DLL załadowanej z opóźnieniem.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. W folderze **konsolidatora** wybierz stronę właściwości **dane wejściowe** .

1. Zmodyfikuj właściwość **bibliotek DLL załadowanych z opóźnieniem** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
