---
description: 'Dowiedz się więcej o: niszczenie okna dialogowego'
title: Niszczenie okna dialogowego
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: f46c86e5f3e869f321b8306470e5821658ceafcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327844"
---
# <a name="destroying-the-dialog-box"></a>Niszczenie okna dialogowego

Modalne okna dialogowe są zwykle tworzone w ramce stosu i niszczone, gdy zostanie ona zakończona. Destruktor obiektu okna dialogowego jest wywoływany, gdy obiekt wykracza poza zakres.

Niemodalne okna dialogowe są zwykle tworzone i są własnością widoku nadrzędnego lub okna ramki — głównego okna ramki aplikacji lub okna ramki dokumentu. Domyślna procedura obsługi [OnClose](reference/cwnd-class.md#onclose) wywołuje [DestroyWindow](reference/cwnd-class.md#destroywindow), co niszczy okno dialogowe. Jeśli okno dialogowe jest samodzielne, bez wskaźników do niego ani do innej semantyki specjalnej własności, należy przesłonić [PostNcDestroy](reference/cwnd-class.md#postncdestroy) , aby zniszczyć obiekt okna dialogowego języka C++. Należy również przesłonić [OnCancel](reference/cdialog-class.md#oncancel) i wywołać `DestroyWindow` je. Jeśli nie, właściciel okna dialogowego powinien zniszczyć obiekt C++, gdy nie jest już potrzebny.

## <a name="see-also"></a>Zobacz też

[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)
