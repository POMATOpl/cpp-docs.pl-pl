---
description: 'Dowiedz się więcej o: Przetwarzaj powiadomienia Header-Control'
title: Przetwarzanie powiadomień dotyczących formantu karty
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: ac1cdbf5efc3e82cdf417a38072cf344ca2ee1a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154854"
---
# <a name="processing-header-control-notifications"></a>Przetwarzanie powiadomień dotyczących formantu karty

W widoku lub klasie okna dialogowego Użyj [kreatora klas](reference/mfc-class-wizard.md) , aby utworzyć funkcję procedury obsługi [OnChildNotify](reference/cwnd-class.md#onchildnotify) z instrukcją Switch dla wszelkich komunikatów powiadomień nagłówka ([CHeaderCtrl](reference/cheaderctrl-class.md)), które chcesz obsłużyć (zobacz [Mapowanie komunikatów do funkcji](reference/mapping-messages-to-functions.md)). Powiadomienia są wysyłane do okna nadrzędnego, gdy użytkownik kliknie lub dwukrotnie kliknie element nagłówka, przeciągnie dzielnika między elementami itd.

Komunikaty powiadomień skojarzone z kontrolką nagłówka są wymienione w temacie [Informacje o formancie nagłówka](/windows/win32/controls/header-control-reference) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHeaderCtrl](using-cheaderctrl.md)<br/>
[Formanty](controls-mfc.md)
