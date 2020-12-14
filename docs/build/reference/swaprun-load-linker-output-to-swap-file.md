---
description: Dowiedz się więcej na temat:/SWAPRUN (ładowanie danych wyjściowych konsolidatora do pliku wymiany)
title: /SWAPRUN (Załaduj pliki wyjściowe konsolidatora do pliku Swap)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: f62d5e32432a2c738b7782c0fbf0cd4fd76a7f9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230214"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Załaduj pliki wyjściowe konsolidatora do pliku Swap)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Uwagi

Opcja/SWAPRUN informuje system operacyjny, aby najpierw skopiował dane wyjściowe konsolidatora do pliku wymiany, a następnie uruchomił obraz stamtąd. Jest to funkcja systemu Windows NT 4,0 (i nowszych).

Jeśli zostanie określona wartość NET, system operacyjny najpierw skopiuje obraz binarny z sieci do pliku wymiany i załaduje go stamtąd. Ta opcja jest przydatna do uruchamiania aplikacji za pośrednictwem sieci. Gdy jest określony dysk CD, system operacyjny skopiuje obraz na dysk wymienny do pliku stronicowania, a następnie załaduje go.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **systemu** .

1. Zmodyfikuj jedną z następujących właściwości:

   - **Zamień przebieg z dysku CD**

   - **Zamień przebieg z sieci**

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> właściwości.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
