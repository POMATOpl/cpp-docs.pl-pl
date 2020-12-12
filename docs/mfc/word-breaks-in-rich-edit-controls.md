---
description: 'Dowiedz się więcej na temat: podziały wyrazów w formantach edycji wzbogaconej'
title: Podziały wyrazów w formantach edycji wzbogaconej
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
ms.openlocfilehash: 662a6b8441c4a9041a539acdabcab74f12d52782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172716"
---
# <a name="word-breaks-in-rich-edit-controls"></a>Podziały wyrazów w formantach edycji wzbogaconej

Kontrolka edycji wzbogaconej ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) wywołuje funkcję o nazwie "procedura dzielenia wyrazów", aby znaleźć przerwy między wyrazami i określić, gdzie może zostać przerwana linia. Kontrolka używa tych informacji podczas wykonywania operacji zawijania tekstu i podczas przetwarzania kombinacji klawiszy CTRL + STRZAŁKA w lewo i CTRL + STRZAŁKA w prawo. Aplikacja może wysyłać komunikaty do kontrolki edycji wzbogaconej, aby zastąpić domyślną procedurę dzielenia wyrazów, aby pobrać informacje o podziale słów i określić, w jakim wierszu znajduje się dany znak.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
