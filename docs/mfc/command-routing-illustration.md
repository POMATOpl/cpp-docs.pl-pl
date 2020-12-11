---
description: 'Dowiedz się więcej o: ilustracja dotycząca routingu poleceń'
title: Ilustracja routingu poleceń
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 51c5182eb1fa2a8b9666e265526e9220a9f3d4a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159963"
---
# <a name="command-routing-illustration"></a>Ilustracja routingu poleceń

Aby zilustrować, rozważ komunikat polecenia z menu Wyczyść wszystko w menu Edycja aplikacji MDI. Załóżmy, że funkcja obsługi dla tego polecenia jest funkcją członkowską klasy dokumentu aplikacji. Oto jak to polecenie dociera do programu obsługi po wybraniu elementu menu przez użytkownika:

1. Okno głównej ramki otrzymuje najpierw komunikat polecenia.

1. Główne okno ramek MDI udostępnia obecnie aktywne okno podrzędne MDI szansa do obsłużenia polecenia.

1. Standardowe Routing okna ramki podrzędnej MDI udostępnia swojemu widokowi szansę na polecenie przed sprawdzeniem własnej mapy komunikatów.

1. Widok sprawdza swoją własną mapę wiadomości, a nie wyszuka żadnej procedury obsługi, a następnie kieruje polecenie do skojarzonego z nim dokumentu.

1. Dokument sprawdza swoją mapę komunikatów i odnajduje procedurę obsługi. Ta funkcja członkowska dokumentu jest wywoływana i Routing zostaje zatrzymany.

Jeśli dokument nie ma procedury obsługi, następnie zostanie dalej rozesłane polecenie do szablonu dokumentu. Następnie polecenie zwróci do widoku, a następnie okno ramki. Na koniec okno ramki sprawdzi swoją mapę komunikatów. Jeśli to sprawdzenie nie powiodło się, polecenie zostanie skierowane z powrotem do głównego okna ramki MDI, a następnie do obiektu aplikacji — ostatecznego miejsca docelowego nieobsługiwanych poleceń.

## <a name="see-also"></a>Zobacz też

[Jak struktura wywołuje program obsługi](how-the-framework-calls-a-handler.md)
