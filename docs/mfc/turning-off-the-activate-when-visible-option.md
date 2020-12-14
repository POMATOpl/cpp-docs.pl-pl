---
description: 'Dowiedz się więcej na temat: wyłączanie opcji Aktywuj, gdy widoczna'
title: Wyłączanie opcji aktywacji w przypadku widoczności
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: fcb5f7ef0518cbf257ef9ee7a659c9617092b7d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263871"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Wyłączanie opcji aktywacji w przypadku widoczności

Kontrolka ma dwa stany podstawowe: aktywne i nieaktywne. Tradycyjnie te Stany były rozróżniane, niezależnie od tego, czy formant miał okno. Aktywna kontrolka miała okno; nieaktywna kontrolka. W przypadku wprowadzenia aktywacji bezokienkowej tego rozróżnienia nie jest już uniwersalne, ale nadal dotyczy wielu kontrolek.

W porównaniu z resztą inicjalizacji zwykle wykonywanej przez kontrolkę ActiveX, tworzenie okna jest niezwykle kosztowną operacją. W idealnym przypadku kontrolka spowoduje odroczenie tworzenia okna do czasu bezwzględnej konieczności.

Wiele kontrolek nie musi być aktywnych cały czas, gdy są one widoczne w kontenerze. Często formant może pozostać w stanie nieaktywnym, dopóki użytkownik nie wykona operacji, która wymaga, aby stała się aktywna (na przykład kliknięcie myszą lub naciśnięcie klawisza TAB). Aby formant pozostały nieaktywny do momentu, gdy kontener będzie wymagał jego aktywowania, Usuń flagę **OLEMISC_ACTIVATEWHENVISIBLE** z flag innych kontrolek:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

Flaga **OLEMISC_ACTIVATEWHENVISIBLE** jest automatycznie pomijana w przypadku wyłączenia opcji Aktywuj, **gdy jest widoczny** na stronie [Ustawienia kontrolki](../mfc/reference/control-settings-mfc-activex-control-wizard.md) kreatora kontrolek ActiveX MFC podczas tworzenia formantu.

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC: Optymalizacja](../mfc/mfc-activex-controls-optimization.md)
