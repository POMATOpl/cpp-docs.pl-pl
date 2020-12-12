---
description: 'Dowiedz się więcej o: Inicjowanie części obiektu CStatusBarCtrl'
title: Inicjowanie części obiektu CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: 52eb738f5fe54a54e54a6415a602a68123869b32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197533"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Inicjowanie części obiektu CStatusBarCtrl

Domyślnie pasek stanu wyświetla informacje o stanie przy użyciu oddzielnych okienek. Te okienka (nazywane również częścią) mogą zawierać ciąg tekstowy, ikonę lub obie te okna.

Użyj elementu [SetParts](reference/cstatusbarctrl-class.md#setparts) , aby zdefiniować, ile części i długości ma mieć pasek stanu. Po utworzeniu części paska stanu, wykonaj wywołania do [SetText](reference/cstatusbarctrl-class.md#settext) i [SetIcon](reference/cstatusbarctrl-class.md#seticon) , aby ustawić tekst lub ikonę dla określonej części paska stanu. Po pomyślnym ustawieniu części kontrolka zostanie automatycznie narysowana ponownie.

Poniższy przykład inicjuje istniejący `CStatusBarCtrl` obiekt ( `m_StatusBarCtrl` ) z czterema okienkami, a następnie ustawia ikonę (IDI_ICON1) i tekst w drugiej części.

[!code-cpp[NVC_MFCControlLadenDialog#31](codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Aby uzyskać więcej informacji na temat ustawiania trybu `CStatusBarCtrl` prostego dla obiektu, zobacz [Ustawianie trybu obiektu CStatusBarCtrl](setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CStatusBarCtrl](using-cstatusbarctrl.md)<br/>
[Formanty](controls-mfc.md)
