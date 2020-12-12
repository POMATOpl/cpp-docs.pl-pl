---
description: Dowiedz się więcej o obsłudze komunikatów i mapowaniu
title: Obsługa i mapowanie komunikatów
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 50a55f4718b47054690325e882177fa9acad2f46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203201"
---
# <a name="message-handling-and-mapping"></a>Obsługa i mapowanie komunikatów

W tym artykule opisano sposób przetwarzania komunikatów i poleceń przez środowisko MFC oraz sposób łączenia ich z funkcjami obsługi.

W tradycyjnych programach dla systemu Windows komunikaty systemu Windows są obsługiwane w dużej instrukcji switch w procedurze okna. MFC zamiast tego używa [map komunikatów](message-categories.md) do mapowania bezpośrednich komunikatów do różnych funkcji składowych klasy. Mapy komunikatów są wydajniejsze niż funkcje wirtualne w tym celu i umożliwiają obsługę komunikatów przez najbardziej odpowiedni obiekt C++ — aplikację, dokument, widok itd. Można mapować pojedynczy komunikat lub zakres komunikatów, identyfikatory poleceń lub identyfikatory formantów.

Komunikaty WM_COMMAND — zwykle generowane przez menu, przyciski paska narzędzi lub akceleratory — również używają mechanizmu mapy komunikatów. MFC definiuje standardowy [Routing](command-routing.md) komunikatów poleceń między aplikacją, oknem ramki, widokiem i aktywnymi dokumentami w programie. W razie potrzeby można przesłonić ten Routing.

Mapy komunikatów również umożliwiają aktualizowanie obiektów interfejsu użytkownika (takich jak menu i przyciski paska narzędzi), Włączanie lub wyłączanie ich w bieżącym kontekście.

Aby uzyskać ogólne informacje o komunikatach i kolejkach komunikatów w systemie Windows, zobacz [komunikaty i kolejki komunikatów](/windows/win32/winmsg/messages-and-message-queues) w Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Komunikaty i polecenia w strukturze](messages-and-commands-in-the-framework.md)

- [Jak struktura wywołuje procedurę obsługi komunikatów](how-the-framework-calls-a-handler.md)

- [Jak struktura wyszukuje mapy komunikatów](how-the-framework-searches-message-maps.md)

- [Deklarowanie funkcji obsługi komunikatów](declaring-message-handler-functions.md)

- [Mapowanie komunikatów do funkcji](reference/mapping-messages-to-functions.md)

- [Jak wyświetlić informacje o poleceniu na pasku stanu](how-to-display-command-information-in-the-status-bar.md)

- [Dynamiczna aktualizacja obiektów interfejsu użytkownika](how-to-update-user-interface-objects.md)

- [Instrukcje: Tworzenie mapy komunikatów dla klasy szablonów](how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Zobacz też

[Pojęcia](mfc-concepts.md)<br/>
[Ogólne tematy dotyczące MFC](general-mfc-topics.md)<br/>
[Klasa CWnd](reference/cwnd-class.md)<br/>
[Klasa CCmdTarget](reference/ccmdtarget-class.md)
