---
description: 'Dowiedz się więcej na temat: User-Interface obiektów i identyfikatorów poleceń'
title: Obiekty interfejsu użytkownika i identyfikatory poleceń
ms.date: 11/19/2018
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
ms.openlocfilehash: 142b72956e0a1b9e60ef48c7db325cd0ac822444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263624"
---
# <a name="user-interface-objects-and-command-ids"></a>Obiekty interfejsu użytkownika i identyfikatory poleceń

Elementy menu, przyciski paska narzędzi i klawisze skrótów są "obiektami interfejsu użytkownika", które mogą generować polecenia. Każdy taki obiekt interfejsu użytkownika ma identyfikator. Obiekt interfejsu użytkownika można skojarzyć z poleceniem, przypisując ten sam identyfikator do obiektu i polecenia. Jak wyjaśniono w [komunikatach](../mfc/messages.md), polecenia są implementowane jako komunikaty specjalne. Rysunek "polecenia w strukturze" poniżej przedstawiają sposób, w jaki struktura zarządza poleceniami. Gdy obiekt interfejsu użytkownika generuje polecenie, takie jak `ID_EDIT_CLEAR_ALL` , jeden z obiektów w aplikacji obsługuje polecenie — na rysunku poniżej, funkcja obiektu dokumentu `OnEditClearAll` jest wywoływana za pośrednictwem mapy komunikatów dokumentu.

![Polecenia w strukturze](../mfc/media/vc385p1.gif "Polecenia w strukturze") <br/>
Polecenia w strukturze

Na rysunku "polecenie aktualizacji w ramach struktury" pokazano, jak biblioteka MFC aktualizuje obiekty interfejsu użytkownika, takie jak elementy menu i przyciski paska narzędzi. Przed wyrzucaniem menu lub w pętli bezczynności w przypadku przycisków paska narzędzi MFC kieruje polecenie Update. Na rysunku poniżej obiekt dokumentu wywołuje procedurę obsługi poleceń aktualizacji, `OnUpdateEditClearAll` , aby włączyć lub wyłączyć obiekt interfejsu użytkownika.

![Aktualizowanie polecenia w strukturze](../mfc/media/vc385p2.png "Aktualizowanie polecenia w strukturze") <br/>
Aktualizowanie polecenia w strukturze

## <a name="see-also"></a>Zobacz też

[Komunikaty i polecenia w strukturze](../mfc/messages-and-commands-in-the-framework.md)
