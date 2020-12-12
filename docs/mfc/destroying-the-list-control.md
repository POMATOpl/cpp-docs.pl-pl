---
description: Dowiedz się więcej o tym, jak zniszczyć formant listy
title: Likwidowanie formantu listy
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: b909889a6365de639f67359859641af6e2bc6525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327837"
---
# <a name="destroying-the-list-control"></a>Likwidowanie formantu listy

Jeśli obiekt [CListCtrl](reference/clistctrl-class.md) zostanie osadzony jako element członkowski danych widoku lub klasy okna dialogowego, zostanie zniszczony, gdy jego właściciel zostanie zniszczony. Jeśli używasz [CListView](reference/clistview-class.md), struktura niszczy formant, gdy niszczy widok.

Jeśli ustawisz dla niektórych danych listy dane, które mają być przechowywane w aplikacji, a nie w kontrolce listy, należy rozmieścić jej cofanie alokacji. Aby uzyskać więcej informacji, zobacz [elementy wywołania zwrotnego i Maska wywołania zwrotnego](/windows/win32/Controls/using-list-view-controls) w Windows SDK.

Ponadto użytkownik jest odpowiedzialny za cofnięcie przydziału list obrazów utworzonych i skojarzonych z obiektem kontrolki listy.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CListCtrl](using-clistctrl.md)<br/>
[Formanty](controls-mfc.md)
