---
description: Dowiedz się więcej o programach obsługi poleceń i powiadomieniach o kontrolkach
title: Programy obsługi dla poleceń i powiadomień dotyczących formantów
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 1e5e3284d5898d1e6349765dc7a1bcdc864c80ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189187"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Programy obsługi dla poleceń i powiadomień dotyczących formantów

Brak domyślnych programów obsługi dla poleceń lub komunikatów kontroli sterowania. W związku z tym użytkownik jest powiązany tylko z konwencją nazewnictwa dla tych kategorii komunikatów. Podczas mapowania polecenia lub powiadomienia o kontrolce do procedury obsługi [Kreator klas](reference/mfc-class-wizard.md) proponuje nazwę na podstawie identyfikatora polecenia lub kodu powiadomienia kontroli. Możesz zaakceptować proponowaną nazwę, zmienić ją lub zastąpić.

Konwencja sugeruje, że programy obsługi nazw są używane w obu kategoriach dla obiektu interfejsu użytkownika, które reprezentują. W ten sposób program obsługi polecenia Wytnij w menu Edycja może być nazwany

[!code-cpp[NVC_MFCMessageHandling#4](codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Ponieważ polecenie Wytnij jest tak często zaimplementowane w aplikacjach, struktura wstępnie definiuje identyfikator polecenia dla polecenia wycinania jako **ID_EDIT_CUT**. Aby uzyskać listę wszystkich wstępnie zdefiniowanych identyfikatorów poleceń, zobacz plik plik AFXRES. H. Aby uzyskać więcej informacji, zobacz [standardowe polecenia](standard-commands.md).

Ponadto Konwencja sugeruje procedurę obsługi komunikatu powiadomienia o **BN_CLICKED** z przycisku oznaczonego "mój przycisk" może mieć nazwę

[!code-cpp[NVC_MFCMessageHandling#5](codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

To polecenie może zostać przypisane do identyfikatora **IDC_MY_BUTTON** , ponieważ jest równoważne obiektowi interfejsu użytkownika określonego dla aplikacji.

Obie kategorie komunikatów nie przyjmują argumentów i nie zwracają żadnej wartości.

## <a name="see-also"></a>Zobacz też

[Deklarowanie funkcji obsługi komunikatów](declaring-message-handler-functions.md)
