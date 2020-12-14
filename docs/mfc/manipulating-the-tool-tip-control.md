---
description: 'Dowiedz się więcej o programie: manipulowanie formantem etykietki narzędzia'
title: Operowanie formantem etykietki narzędzia
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: f04a2a9fe7d9b32d4b0fab1c6fea0d82f48cbf1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281070"
---
# <a name="manipulating-the-tool-tip-control"></a>Operowanie formantem etykietki narzędzia

Klasa `CToolTipCtrl` udostępnia grupę funkcji Członkowskich kontrolujących różne atrybuty `CToolTipCtrl` obiektu i okna etykietki narzędzia.

Początkowe, wyskakujące okienka i ponowne wyświetlanie dla okien etykietek narzędzi można ustawić i pobrać z wywołaniami do [GetDelayTime](reference/ctooltipctrl-class.md#getdelaytime) i [SetDelayTime](reference/ctooltipctrl-class.md#setdelaytime).

Zmień wygląd okien etykietek narzędzi z następującymi funkcjami:

- [GetMargin](reference/ctooltipctrl-class.md#getmargin) i [SetMargin](reference/ctooltipctrl-class.md#setmargin) pobierają i ustawia szerokość między obramowaniem etykietki narzędzia a tekstem etykietki narzędzia.

- [GetMaxTipWidth](reference/ctooltipctrl-class.md#getmaxtipwidth) i [SetMaxTipWidth](reference/ctooltipctrl-class.md#setmaxtipwidth) pobiera i ustawia maksymalną szerokość okna etykietki narzędzia.

- [GetTipBkColor](reference/ctooltipctrl-class.md#gettipbkcolor) i [SetTipBkColor](reference/ctooltipctrl-class.md#settipbkcolor) pobiera i ustawia kolor tła okna etykietki narzędzia.

- [GetTipTextColor](reference/ctooltipctrl-class.md#gettiptextcolor) i [SetTipTextColor](reference/ctooltipctrl-class.md#settiptextcolor) pobiera i ustawia kolor tekstu okna etykietki narzędzia.

Aby formant etykietki narzędzia był powiadamiany o ważnych komunikatach, takich jak komunikaty WM_LBUTTONXXX, należy przekazać komunikaty do kontrolki etykietki narzędzia. Najlepszą metodą dla tego przekaźnika jest wywołanie [CToolTipCtrl:: RelayEvent](reference/ctooltipctrl-class.md#relayevent)w `PreTranslateMessage` funkcji okna właściciela. Poniższy przykład ilustruje jedną możliwą metodę (przy założeniu, że kontrolka etykietki narzędzia jest wywoływana `m_ToolTip` ):

[!code-cpp[NVC_MFCControlLadenDialog#41](codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

Aby natychmiast usunąć okno etykietki narzędzi, wywołaj funkcję elementu członkowskiego [pop](reference/ctooltipctrl-class.md#pop) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CToolTipCtrl](using-ctooltipctrl.md)<br/>
[Formanty](controls-mfc.md)
