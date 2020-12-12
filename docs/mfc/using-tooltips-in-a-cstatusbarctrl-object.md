---
description: 'Dowiedz się więcej na temat: używanie etykietek narzędzi w obiekcie CStatusBarCtrl'
title: Używanie etykietek narzędzi w obiekcie CStatusBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: d77610a511698000dc70a1aa1cb1edb22fb3eb7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143250"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Używanie etykietek narzędzi w obiekcie CStatusBarCtrl

Aby włączyć etykietki narzędzi dla kontrolki pasek stanu, Utwórz `CStatusBarCtrl` obiekt z stylem SBT_TOOLTIPS.

> [!NOTE]
> Jeśli używasz `CStatusBar` obiektu do zaimplementowania paska stanu, użyj `CStatusBar::CreateEx` funkcji. Umożliwia określenie dodatkowych stylów dla osadzonego `CStatusBarCtrl` obiektu.

Po `CStatusBarCtrl` pomyślnym utworzeniu obiektu Użyj [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) i [CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) , aby ustawić i pobrać tekst porady dla określonego okienka.

Po ustawieniu etykietki narzędzia jest wyświetlana tylko wtedy, gdy część ma ikonę i nie ma tekstu, lub jeśli nie można wyświetlić całego tekstu w części. Etykietki narzędzi nie są obsługiwane w trybie prostym.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
