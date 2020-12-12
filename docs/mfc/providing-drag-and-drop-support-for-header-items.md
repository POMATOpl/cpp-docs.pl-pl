---
description: 'Dowiedz się więcej o: zapewnianie obsługi przeciągania i upuszczania w przypadku elementów nagłówka'
title: Zapewnianie obsługi przeciągania i upuszczania w przypadku elementów nagłówka
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: ed42f61220ee2033dbc36e11c18664be3968dddd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248791"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Zapewnianie obsługi przeciągania i upuszczania w przypadku elementów nagłówka

Aby zapewnić obsługę przeciągania i upuszczania dla elementów nagłówka, określ styl HDS_DRAGDROP. Obsługa przeciągania i upuszczania dla elementów nagłówka daje użytkownikowi możliwość zmiany kolejności elementów nagłówka kontrolki nagłówka. Zachowanie domyślne zapewnia półprzezroczyste przeciąganie obrazu elementu nagłówka, który jest przeciągany oraz wskaźnik wizualizacji nowej pozycji, jeśli element nagłówka zostanie porzucony.

Podobnie jak w przypadku typowych funkcji przeciągania i upuszczania, można zwiększyć domyślne zachowanie przeciągania i upuszczania poprzez obsługę HDN_BEGINDRAG i HDN_ENDDRAG powiadomienia. Możesz również dostosować wygląd obrazu przeciąganego, zastępując funkcję członkowską [CHeaderCtrl:: CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) .

> [!NOTE]
> Jeśli zapewniasz obsługę przeciągania i upuszczania dla osadzonego formantu nagłówka w kontrolce lista, zobacz sekcję styl rozszerzony w temacie [Zmiana stylów formantu listy](../mfc/changing-list-control-styles.md) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHeaderCtrl](../mfc/using-cheaderctrl.md)
