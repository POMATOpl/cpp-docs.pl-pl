---
description: 'Dowiedz się więcej o programie: identyfikatory poleceń'
title: Identyfikatory poleceń
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: bba3b8b342b4d2e0c9492f9d0f3100a5d8f9e7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159989"
---
# <a name="command-ids"></a>Identyfikatory poleceń

Polecenie jest w pełni opisane za pomocą samego identyfikatora polecenia (zakodowane w wiadomości **WM_COMMAND** ). Ten identyfikator jest przypisany do obiektu interfejsu użytkownika, który generuje polecenie. Zwykle identyfikatory są nazywane dla funkcji obiektu interfejsu użytkownika, do którego są przypisane.

Na przykład Wyczyść wszystkie elementy w menu Edycja mogą mieć przypisany identyfikator, taki jak **ID_EDIT_CLEAR_ALL**. Biblioteka klas wstępnie definiuje niektóre identyfikatory, szczególnie dla poleceń obsługiwanych przez platformę, takich jak **ID_EDIT_CLEAR_ALL** lub **ID_FILE_OPEN**. Inne identyfikatory poleceń utworzysz samodzielnie.

Gdy tworzysz własne menu w edytorze menu Visual C++, dobrym pomysłem jest przestrzeganie konwencji nazewnictwa biblioteki klas, jak pokazano na **ID_FILE_OPEN**. [Standardowe polecenia](standard-commands.md) objaśniają standardowe polecenia zdefiniowane przez bibliotekę klas.

## <a name="see-also"></a>Zobacz też

[Obiekty interfejsu użytkownika i identyfikatory poleceń](user-interface-objects-and-command-ids.md)
