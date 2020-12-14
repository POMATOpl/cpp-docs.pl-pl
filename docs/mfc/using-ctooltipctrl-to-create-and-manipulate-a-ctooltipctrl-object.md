---
description: 'Dowiedz się więcej na temat: używanie CToolTipCtrl do tworzenia obiektu CToolTipCtrl i manipulowania nim'
title: Używanie formantu CToolTipCtrl do tworzenia obiektu CToolTipCtrl i operowania nim
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: 363d46ce078b71cf88d742ae390ab674a73ab935
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202343"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Używanie formantu CToolTipCtrl do tworzenia obiektu CToolTipCtrl i operowania nim

Oto przykład użycia [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) :

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Tworzenie i manipulowanie CToolTipCtrl

1. Konstruowanie `CToolTipCtrl` obiektu.

1. Wywołanie [Create](../mfc/reference/ctooltipctrl-class.md#create) w celu utworzenia typowej kontrolki narzędzia systemu Windows i dołączenie jej do `CToolTipCtrl` obiektu.

1. Wywołaj [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) , aby zarejestrować narzędzie za pomocą kontrolki etykietki narzędzia, tak aby informacje przechowywane w etykietce narzędzia były wyświetlane po umieszczeniu kursora w narzędziu.

1. Wywołaj [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) , aby ustawić informacje, które są przechowywane w etykietce narzędzia dla narzędzia.

1. Wywołaj [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) , aby ustawić nowy prostokąt ograniczający dla narzędzia.

1. Wywołaj [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) w celu przetestowania punktu, aby określić, czy znajduje się on w obrębie obwiedni danego narzędzia, a jeśli tak, Pobierz informacje o narzędziu.

1. Wywołaj [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) , aby pobrać liczbę narzędzi zarejestrowanych w kontrolce etykietki narzędzia.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
