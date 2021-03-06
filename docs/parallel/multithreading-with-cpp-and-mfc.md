---
description: 'Dowiedz się więcej na temat: Wielowątkowość z C++ i MFC'
title: Wielowątkowość z C++ i MFC
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
ms.openlocfilehash: a553f6364f52ce8d91e08e3bb5b0e83b48575fdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149815"
---
# <a name="multithreading-with-c-and-mfc"></a>Wielowątkowość z C++ i MFC

Biblioteka Microsoft Foundation Class (MFC) zapewnia obsługę aplikacji wielowątkowych. W tym temacie opisano procesy i wątki oraz podejście MFC do wielowątkowości.

Proces jest wykonywanym wystąpieniem aplikacji. Na przykład po dwukrotnym kliknięciu ikony Notatnika zostanie uruchomiony proces z uruchomionym programem Notatnik.

Wątek jest ścieżką wykonania w ramach procesu. Po uruchomieniu Notatnika system operacyjny tworzy proces i rozpoczyna wykonywanie wątku podstawowego tego procesu. Po zakończeniu tego wątku proces jest przetwarzany. Ten wątek podstawowy jest dostarczany do systemu operacyjnego przez kod uruchamiania w postaci adresu funkcji. Zwykle jest to adres `main` lub `WinMain` Funkcja, która została dostarczona.

Jeśli chcesz, możesz utworzyć dodatkowe wątki w aplikacji. Można to zrobić, aby obsłużyć zadania w tle lub konserwacji, gdy użytkownik nie chce czekać na ich zakończenie. Wszystkie wątki w aplikacjach MFC są reprezentowane przez obiekty [CWinThread](../mfc/reference/cwinthread-class.md) . W większości sytuacji nie trzeba nawet jawnie tworzyć tych obiektów; Zamiast tego wywołaj funkcję pomocnika struktury [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), która tworzy `CWinThread` obiekt.

MFC odróżnia dwa typy wątków: wątki interfejsu użytkownika i wątki robocze. Wątki interfejsu użytkownika są często używane do obsługi danych wejściowych użytkownika i reagowania na zdarzenia i komunikaty generowane przez użytkownika. Wątki robocze są często używane do wykonywania zadań, takich jak ponowne obliczanie, które nie wymagają danych wejściowych użytkownika. Win32 API nie rozróżnia typów wątków; wystarczy znać adres początkowy wątku, aby można było rozpocząć wykonywanie wątku. MFC obsługuje wątki interfejsu użytkownika specjalnie przez dostarczanie pompy komunikatów dla zdarzeń w interfejsie użytkownika. `CWinApp` jest przykładem obiektu wątku interfejsu użytkownika, ponieważ pochodzi od `CWinThread` i obsługuje zdarzenia i komunikaty generowane przez użytkownika.

Szczególną uwagę należy zwrócić na sytuacje, w których więcej niż jeden wątek może wymagać dostępu do tego samego obiektu. [Wielowątkowość: porady dotyczące programowania](multithreading-programming-tips.md) opisują techniki, których można użyć w celu obejścia problemów, które mogą wystąpić w tych sytuacjach. [Wielowątkowość: jak używać klas synchronizacji](multithreading-how-to-use-the-synchronization-classes.md) opisuje sposób używania klas, które są dostępne do synchronizowania dostępu z wielu wątków do pojedynczego obiektu.

Pisanie i debugowanie programowania wielowątkowego jest w sposób niezależny i niezależny od przedsiębiorstwa, ponieważ należy upewnić się, że obiekty nie są dostępne przez więcej niż jeden wątek w danym momencie. Tematy dotyczące wielowątkowości nie uczyją się podstaw programowania wielowątkowego, tylko sposobu korzystania z MFC w programie wielowątkowym. Wielowątkowe przykłady MFC zawarte w Visual C++ ilustrują kilka wielowątkowych możliwości dodawania funkcji i interfejsów API Win32, które nie są objęte MFC; Jednak są one przeznaczone tylko do punktu początkowego.

Aby uzyskać więcej informacji o tym, jak system operacyjny obsługuje procesy i wątki, zobacz [procesy i wątki](/windows/win32/ProcThread/processes-and-threads) w Windows SDK.

Więcej informacji o obsłudze wielowątkowości MFC znajduje się w następujących tematach:

- [Wielowątkowość: Tworzenie wątków User-Interface](multithreading-creating-user-interface-threads.md)

- [Wielowątkowość: Tworzenie wątków roboczych](multithreading-creating-worker-threads.md)

- [Wielowątkowość: jak używać klas synchronizacji](multithreading-how-to-use-the-synchronization-classes.md)

- [Wielowątkowość: przerywanie wątków](multithreading-terminating-threads.md)

- [Wielowątkowość: porady dotyczące programowania](multithreading-programming-tips.md)

- [Wielowątkowość: Kiedy używać klas synchronizacji](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>Zobacz też

[Obsługa wielowątkowości w przypadku starszego kodu (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)
