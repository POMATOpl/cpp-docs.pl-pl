---
description: 'Dowiedz się więcej o programie: implikacje zabezpieczeń dotyczące dostosowywania'
title: Konsekwencje dostosowania związane z zabezpieczeniami
ms.date: 11/04/2016
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
ms.openlocfilehash: 64a1029dd3486e3cd653f5e692aa1a14ba6f82b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217760"
---
# <a name="security-implications-of-customization"></a>Konsekwencje dostosowania związane z zabezpieczeniami

W tym temacie omówiono potencjalne luki w zabezpieczeniach MFC.

## <a name="potential-security-weakness"></a>Potencjalna słabość zabezpieczeń

MFC umożliwia użytkownikowi dostosowanie wyglądu interfejsu użytkownika aplikacji, na przykład wyglądu przycisków i ikon. MFC obsługuje także narzędzia zdefiniowane przez użytkownika, które umożliwiają wykonywanie poleceń powłoki przez użytkownika. Występuje luka w zabezpieczeniach, ponieważ dostosowane ustawienia aplikacji są zapisywane w profilu użytkownika w rejestrze. Każdy użytkownik, który ma dostęp do rejestru, może edytować te ustawienia i zmieniać wygląd lub zachowanie aplikacji. Na przykład administrator na komputerze może personifikować użytkownika, powodując, że aplikacja użytkownika ma wykonywać dowolne programy (nawet z udziału sieciowego).

## <a name="workarounds"></a>Obejścia

Zalecamy dowolnych z tych trzech metod zamykania luk w zabezpieczeniach rejestru:

- Szyfruj dane przechowywane w tym miejscu

- Przechowuj dane w zabezpieczonym pliku zamiast w rejestrze.

   Aby wykonać jedną z dwóch pierwszych metod, należy utworzyć klasę z [klasy CSettingsStore](../mfc/reference/csettingsstore-class.md) i zastąpić jej metody w celu zaimplementowania szyfrowania lub magazynu poza rejestrem.

- Możesz również wyłączyć dostosowania w aplikacji.

## <a name="see-also"></a>Zobacz też

[Dostosowywanie na potrzeby MFC](../mfc/customization-for-mfc.md)
