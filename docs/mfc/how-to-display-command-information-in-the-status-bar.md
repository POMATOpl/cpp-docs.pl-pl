---
description: 'Dowiedz się więcej na temat: Instrukcje: wyświetlanie informacji o poleceniu na pasku stanu'
title: 'Porady: wyświetlanie informacji o poleceniu na pasku stanu'
ms.date: 11/04/2016
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
ms.openlocfilehash: 568e8d356659d5267e8c4947f2981cd6243a7056
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330216"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Porady: wyświetlanie informacji o poleceniu na pasku stanu

Po uruchomieniu Kreatora aplikacji w celu utworzenia szkieletu aplikacji można obsługiwać pasek narzędzi i pasek stanu. W Kreatorze aplikacji jest obsługiwana tylko jedna opcja. Gdy jest obecny pasek stanu, aplikacja automatycznie zapewnia przydatne informacje zwrotne, gdy użytkownik przesuwa wskaźnik nad elementami w menu. Aplikacja automatycznie wyświetla ciąg monitu na pasku stanu, gdy element menu zostanie wyróżniony. Na przykład gdy użytkownik przesuwa wskaźnik nad poleceniem **wycinania** w menu **Edycja** , na pasku stanu może być wyświetlany komunikat "wycina zaznaczenie i umieszcza je w schowku" w obszarze komunikatów na pasku statusu. Monit pomaga użytkownikowi zrozumieć cel elementu menu. Działa to również wtedy, gdy użytkownik kliknie przycisk paska narzędzi.

Możesz dodać do tej pomocy na pasku stanu, definiując ciągi monitów dla elementów menu dodawanych do programu. W tym celu Podaj ciągi monitu podczas edycji właściwości elementu menu w edytorze menu. Definiowane ciągi są przechowywane w pliku zasobów aplikacji. mają one takie same identyfikatory, jak polecenia objaśniające.

Domyślnie Kreator aplikacji dodaje **AFX_IDS_IDLEMESSAGE**, identyfikator standardowego komunikatu "gotowe", który jest wyświetlany, gdy program czeka na nowe komunikaty. Jeśli określisz opcję pomocy Context-Sensitive w Kreatorze aplikacji, komunikat zostanie zmieniony na "Aby uzyskać pomoc, naciśnij klawisz F1".

## <a name="see-also"></a>Zobacz też

[Obsługa i mapowanie komunikatów](message-handling-and-mapping.md)
