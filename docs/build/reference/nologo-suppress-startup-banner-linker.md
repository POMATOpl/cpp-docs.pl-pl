---
description: Dowiedz się więcej o:/NOLOGO (Pomijaj transparent startowy) (Konsolidator)
title: /NOLOGO (Pomiń transparent początkowy) (Konsolidator)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: 48edea691e254f0754d29ab5ea4d8055221c4b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196558"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Pomiń transparent początkowy) (Konsolidator)

```
/NOLOGO
```

## <a name="remarks"></a>Uwagi

Opcja/NOLOGO uniemożliwia wyświetlanie komunikatu o prawach autorskich i numeru wersji.

Ta opcja powoduje również pominięcie ECHA plików poleceń. Aby uzyskać szczegółowe informacje, zobacz [pliki poleceń link](linking.md).

Domyślnie te informacje są wysyłane przez konsolidator do okna danych wyjściowych. W wierszu polecenia jest wysyłany do wyjścia standardowego i może być przekierowywany do pliku.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Tej opcji należy używać tylko w wierszu polecenia.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Nie można programowo zmienić tej opcji konsolidatora.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
