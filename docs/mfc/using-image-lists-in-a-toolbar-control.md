---
description: 'Dowiedz się więcej o programie: Używanie list obrazów w formancie paska narzędzi'
title: Używanie list obrazów w formancie paska narzędzi
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: dbdac26f1d17997e14ed4ba16875ef3794e46a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154438"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Używanie list obrazów w formancie paska narzędzi

Domyślnie obrazy używane przez przyciski w kontrolce paska narzędzi są przechowywane jako pojedyncze mapy bitowe. Można jednak przechowywać obrazy przycisków na zestawie list obrazów. Obiekt formantu Toolbar może używać maksymalnie trzech oddzielnych list obrazów:

- Lista włączonych obrazów zawiera obrazy dla przycisków paska narzędzi, które są obecnie włączone.

- Lista wyłączonych obrazów zawiera obrazy dla przycisków paska narzędzi, które są obecnie wyłączone.

- Lista wyróżnionych obrazów zawiera obrazy przycisków paska narzędzi, które są obecnie wyróżnione. Ta lista obrazów jest używana tylko wtedy, gdy na pasku narzędzi jest używany styl TBSTYLE_FLAT.

Te listy obrazów są używane przez formant Toolbar po skojarzeniu ich z `CToolBarCtrl` obiektem. To skojarzenie jest realizowane przez wykonywanie wywołań do [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)i [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).

Domyślnie MFC używa `CToolBar` klasy do implementowania pasków narzędzi aplikacji MFC. Jednak `GetToolBarCtrl` funkcja członkowska może służyć do pobierania osadzonego `CToolBarCtrl` obiektu. Następnie można wykonywać wywołania `CToolBarCtrl` funkcji Członkowskich przy użyciu zwróconego obiektu.

Poniższy przykład ilustruje tę technikę, przypisując `m_ToolBarImages` listę obrazów Enabled () i disabled ( `m_ToolBarDisabledImages` ) do `CToolBarCtrl` obiektu ( `m_ToolBarCtrl` ).

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> Listy obrazów używane przez obiekt Toolbar muszą być trwałymi obiektami. Z tego powodu często są elementami członkowskimi danych klasy MFC; w tym przykładzie główna Klasa okna ramki.

Gdy listy obrazów są skojarzone z `CToolBarCtrl` obiektem, struktura automatycznie wyświetla odpowiedni obraz przycisku.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
