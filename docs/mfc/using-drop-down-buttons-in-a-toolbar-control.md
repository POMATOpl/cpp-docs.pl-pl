---
description: 'Dowiedz się więcej na temat: Używanie przycisków Drop-Down w formancie paska narzędzi'
title: Używanie przycisków listy rozwijanej w formancie paska narzędzi
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: a37f39397f6b6f66bed1ad1d2fbd9530b55f3d7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154464"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Używanie przycisków listy rozwijanej w formancie paska narzędzi

Oprócz standardowych przycisków wypychania pasek narzędzi może również mieć przyciski rozwijane. Przycisk listy rozwijanej jest zwykle wskazywany przez obecność dołączonej strzałki w dół.

> [!NOTE]
> Dołączona Strzałka w dół zostanie wyświetlona tylko wtedy, gdy ustawiono TBSTYLE_EX_DRAWDDARROWS stylu rozszerzonego.

Gdy użytkownik kliknie tę strzałkę (lub sam przycisk, jeśli nie ma żadnej strzałki), do elementu nadrzędnego formantu Toolbar zostanie wysłana wiadomość z powiadomieniem TBN_DROPDOWN. Następnie można obsłużyć to powiadomienie i wyświetlić menu podręczne. przypomina zachowanie programu Internet Explorer.

W poniższej procedurze pokazano, jak zaimplementować przycisk paska narzędzi listy rozwijanej z menu podręcznym:

### <a name="to-implement-a-drop-down-button"></a>Aby zaimplementować przycisk listy rozwijanej

1. Po `CToolBarCtrl` utworzeniu obiektu Ustaw styl TBSTYLE_EX_DRAWDDARROWS przy użyciu następującego kodu:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. Ustaw styl TBSTYLE_DROPDOWN dla każdego nowego ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) lub [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) lub istniejących przycisków ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)), które będą przyciskami listy rozwijanej. Poniższy przykład demonstruje modyfikowanie istniejącego przycisku w `CToolBarCtrl` obiekcie:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Dodaj procedurę obsługi TBN_DROPDOWN do klasy nadrzędnej obiektu Toolbar.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. W obszarze nowy program obsługi Wyświetl odpowiednie menu podręczne. Poniższy kod ilustruje jedną metodę:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
