---
description: 'Dowiedz się więcej na temat: Wybór elementu kontrolki drzewa'
title: Wybór elementu kontrolki drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 46e1256eea3e8175b996a1b6bdfdd7c1de2739d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264040"
---
# <a name="tree-control-item-selection"></a>Wybór elementu kontrolki drzewa

Gdy zaznaczenie zostanie zmienione z jednego elementu na inny, formant drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) wysyła [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) i [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) komunikatów powiadomień. Obie powiadomienia obejmują wartość określającą, czy zmiana jest wynikiem kliknięcia myszą, czy naciśnięciem klawisza. Powiadomienia obejmują również informacje o elemencie, który uzyskuje zaznaczenie i element, który utraci zaznaczenie. Korzystając z tych informacji, można ustawić atrybuty elementu, które zależą od stanu zaznaczenia elementu. Zwrócenie **wartości true** w odpowiedzi `TVN_SELCHANGING` uniemożliwia zmianę zaznaczenia; zwrócenie **wartości false** umożliwia zmianę.

Aplikacja może zmienić zaznaczenie, wywołując funkcję elementu członkowskiego [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
