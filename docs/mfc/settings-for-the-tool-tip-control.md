---
description: 'Dowiedz się więcej na temat: ustawienia kontrolki etykietki narzędzia'
title: Ustawienia formantu etykietki narzędzia
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
ms.openlocfilehash: 789f33a7e8e960f52589588bcda49a12889fa0d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217032"
---
# <a name="settings-for-the-tool-tip-control"></a>Ustawienia formantu etykietki narzędzia

Kontrolkę etykietki narzędzia ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) można ustawić jako aktywną lub nieaktywną. Gdy ustawisz ją jako aktywną, formant etykietki narzędzia pojawia się, gdy kursor znajduje się w narzędziu. Gdy ustawisz jako nieaktywny, formant etykietki narzędzia nie jest wyświetlany, nawet jeśli kursor znajduje się w narzędziu. Wywołaj [aktywację](../mfc/reference/ctooltipctrl-class.md#activate) , aby aktywować lub dezaktywować formant etykietki narzędzia.

Możesz ustawić aktywną etykietkę narzędzia, aby wyświetlić etykietkę narzędzia, gdy kursor znajduje się w narzędziu, niezależnie od tego, czy okno właściciela kontrolki etykietki narzędzia jest aktywne, czy nieaktywne, przy użyciu stylu TTS_ALWAYSTIP. Jeśli ten styl nie jest używany, formant etykietki narzędzia pojawia się, gdy okno właściciela narzędzia jest aktywne, ale nie w nieaktywnym czasie.

Większość aplikacji zawiera paski narzędzi z narzędziami, które odpowiadają poleceniom menu. W przypadku takich narzędzi jest wygodne, aby formant etykietki narzędzia wyświetlał ten sam tekst co odpowiadający element menu. System automatycznie łączy znaki akceleratora handlowego "i" (&) ze wszystkich ciągów przesyłanych do kontrolki etykietki narzędzia, chyba że formant ma styl TTS_NOPREFIX.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
