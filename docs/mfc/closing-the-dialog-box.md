---
description: 'Dowiedz się więcej na temat: zamykanie okna dialogowego'
title: Zamykanie okna dialogowego
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 4e60bdfb1ecb6968996d6c657f0c667ad2686a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338366"
---
# <a name="closing-the-dialog-box"></a>Zamykanie okna dialogowego

Modalne okno dialogowe jest zamykane, gdy użytkownik wybierze jeden z przycisków, zazwyczaj przycisk OK lub przycisk Anuluj. Wybranie przycisku OK lub Anuluj powoduje, że system Windows wyśle do obiektu okna dialogowego komunikat z powiadomieniem o **BN_CLICKED** kontrolki z identyfikatorem przycisku ( **IDOK** lub **IDCANCEL**). `CDialog` udostępnia domyślne funkcje programu obsługi dla tych komunikatów: `OnOK` i `OnCancel` . Domyślne programy obsługi wywołują `EndDialog` funkcję członkowską, aby zamknąć okno dialogowe. Możesz również wywołać `EndDialog` z własnego kodu. Aby uzyskać więcej informacji, zobacz funkcja członkowska [zdarzenie EndDialog](reference/cdialog-class.md#enddialog) klasy `CDialog` w *Kompendium MFC*.

Aby rozmieścić Zamknij i usunąć niemodalne okno dialogowe, Przesłoń `PostNcDestroy` i Wywołaj **`delete`** operator na **`this`** wskaźniku. [Niszczenie okna dialogowego wyjaśnia,](destroying-the-dialog-box.md) co się dzieje.

## <a name="see-also"></a>Zobacz też

[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)
