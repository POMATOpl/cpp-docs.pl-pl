---
description: 'Dowiedz się więcej na temat: Praca z formantem paska narzędzi'
title: Praca z formantem paska narzędzi
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: bb5b14b35deeff515468a16c82a606704300a395
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197468"
---
# <a name="working-with-the-toolbar-control"></a>Praca z formantem paska narzędzi

W tym artykule wyjaśniono, jak uzyskać dostęp do obiektu [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) bazowego [CToolBar](../mfc/reference/ctoolbar-class.md) w celu uzyskania większej kontroli nad paskami narzędzi. To jest zaawansowany temat.

## <a name="procedures"></a>Procedury

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>Aby uzyskać dostęp do typowej kontrolki paska narzędzi leżącej pod obiektem CToolBar

1. Wywołanie [CToolBar:: GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl` Zwraca odwołanie do obiektu [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) . Można użyć odwołania do wywołania funkcji członkowskich klasy formantu Toolbar.

> [!CAUTION]
> Gdy wywoływanie `CToolBarCtrl` funkcji **Get** jest bezpieczne, należy zachować ostrożność w przypadku wywołania funkcji **Set** . To jest zaawansowany temat. Zwykle nie trzeba uzyskiwać dostępu do podstawowego formantu paska narzędzi.

### <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Kontrolki (formanty standardowe systemu Windows)](../mfc/controls-mfc.md)

- [Paski narzędzi — podstawowe założenia](../mfc/toolbar-fundamentals.md)

- [Zadokowane i przestawne paski narzędzi](../mfc/docking-and-floating-toolbars.md)

- [Dynamiczne zmienianie rozmiarów paska narzędzi](../mfc/docking-and-floating-toolbars.md)

- [Etykietki narzędzi paska narzędzi](../mfc/toolbar-tool-tips.md)

- [Aktualizacje paska stanu Flyby](../mfc/toolbar-tool-tips.md)

- [Obsługa powiadomień dotyczących etykietek narzędzi](../mfc/handling-tool-tip-notifications.md)

- Klasy [CToolBar](../mfc/reference/ctoolbar-class.md) i [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [Obsługa powiadomień dotyczących dostosowania](../mfc/handling-customization-notifications.md)

- [Wiele pasków narzędzi](../mfc/toolbar-fundamentals.md)

- [Używanie swoich starych pasków narzędzi](../mfc/using-your-old-toolbars.md)

- [Paski sterowania](../mfc/control-bars.md)

Aby uzyskać ogólne informacje dotyczące korzystania z formantów wspólnych systemu Windows, zobacz temat [typowe formanty](/windows/win32/Controls/common-controls-intro).

## <a name="see-also"></a>Zobacz też

[Implementacja paska narzędzi MFC](../mfc/mfc-toolbar-implementation.md)
