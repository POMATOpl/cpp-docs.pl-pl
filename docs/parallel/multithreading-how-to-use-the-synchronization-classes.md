---
description: 'Dowiedz się więcej o: Wielowątkowość: jak używać klas synchronizacji MFC'
title: 'Wielowątkowość: jak używać klas synchronizacji MFC'
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [MFC], synchronization classes
- resources [C++], multithreading
- thread-safe classes [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], thread-safe class design
- threading [C++], synchronization
- multithreading [C++], synchronization classes
- threading [C++], thread-safe class design
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
ms.openlocfilehash: a62bdba992ef8b65c14991da26e098f545c30ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149919"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>Wielowątkowość: jak używać klas synchronizacji MFC

Synchronizowanie dostępu do zasobów między wątkami jest typowym problemem podczas pisania aplikacji wielowątkowych. Posiadanie dwóch lub więcej wątków jednocześnie dostępu do tych samych danych może prowadzić do niepożądanych i nieprzewidywalnych wyników. Na przykład jeden wątek może aktualizować zawartość struktury, podczas gdy inny wątek odczytuje zawartość tej samej struktury. Nieznane dane, które otrzymają wątek odczytywania: stare dane, nowo wpisane dane lub możliwe mieszanki obu tych elementów. MFC zapewnia wiele klas dostępu synchronizacji i synchronizacji, aby pomóc w rozwiązaniu tego problemu. W tym temacie objaśniono dostępne klasy i sposoby ich używania do tworzenia klas bezpiecznych dla wątków w typowej aplikacji wielowątkowej.

Typowa aplikacja wielowątkowa ma klasę, która reprezentuje zasób, który ma być współużytkowany między wątkami. Prawidłowo zaprojektowana, w pełni bezpieczna wątek Klasa nie wymaga wywołania żadnych funkcji synchronizacji. Wszystkie elementy są obsługiwane wewnętrznie dla klasy, co pozwala skoncentrować się na najlepszym użyciu klasy, a nie o sposobie ich uszkodzenia. Skuteczna technika tworzenia w pełni bezpiecznej wątkowej klasy polega na scaleniu klasy synchronizacji z klasą zasobów. Scalanie klas synchronizacji do klasy udostępnionej jest procesem prostym.

Na przykład Utwórz aplikację, która utrzymuje połączoną listę kont. Ta aplikacja umożliwia przeanalizowanie maksymalnie trzech kont w oddzielnych oknach, ale tylko jeden z nich można zaktualizować w określonym czasie. W przypadku zaktualizowania konta zaktualizowane dane są wysyłane przez sieć do archiwum danych.

Ta przykładowa aplikacja używa wszystkich trzech typów klas synchronizacji. Ponieważ umożliwia badanie maksymalnie trzech kont jednocześnie, używa [CSemaphore](../mfc/reference/csemaphore-class.md) , aby ograniczyć dostęp do trzech obiektów widoku. Podczas próby wyświetlenia czwartego konta następuje odczekanie, aż jeden z trzech pierwszych okien zostanie zamknięty lub zakończy się niepowodzeniem. Gdy konto zostanie zaktualizowane, aplikacja używa [CCriticalSection](../mfc/reference/ccriticalsection-class.md) , aby zapewnić, że tylko jedno konto jest aktualizowane jednocześnie. Po pomyślnym zakończeniu aktualizacji program sygnalizuje [CEvent](../mfc/reference/cevent-class.md), który zwalnia wątek oczekujący na zasygnalizowanie zdarzenia. Ten wątek wysyła nowe dane do archiwum danych.

## <a name="designing-a-thread-safe-class"></a><a name="_mfc_designing_a_thread.2d.safe_class"></a> Projektowanie klasy Thread-Safe

Aby zapewnić pełną wielowątkowość klasy, należy najpierw dodać odpowiednią klasę synchronizacji do klas udostępnionych jako element członkowski danych. W poprzednim przykładzie zarządzania kontem `CSemaphore` do klasy widoku zostanie dodany element członkowski danych, a element członkowski danych zostanie dodany do klasy `CCriticalSection` połączonej listy, a `CEvent` element członkowski danych zostanie dodany do klasy magazynu danych.

Następnie Dodaj wywołania synchronizacji do wszystkich funkcji Członkowskich, które modyfikują dane w klasie lub uzyskują dostęp do kontrolowanego zasobu. W każdej funkcji należy utworzyć obiekt [CSingleLock](../mfc/reference/csinglelock-class.md) lub [CMultiLock](../mfc/reference/cmultilock-class.md) , a następnie wywołać funkcję tego obiektu `Lock` . Gdy obiekt blokady wykracza poza zakres i jest niszczony, destruktor obiektu wywołuje `Unlock` Cię, zwalniając zasób. Oczywiście możesz wywoływać bezpośrednio, `Unlock` Jeśli chcesz.

Projektowanie klas bezpiecznych dla wątków w ten sposób umożliwia korzystanie z aplikacji wielowątkowych jako niebezpiecznej do wątku klasy, ale przy wyższym poziomie bezpieczeństwa. Hermetyzowanie obiektu synchronizacji i obiektu dostępu do synchronizacji z klasą zasobów zapewnia wszystkie korzyści płynące z całkowicie bezpiecznego programowania wątków bez konieczności utrzymywania kodu synchronizacji.

Poniższy przykład kodu demonstruje tę metodę przy użyciu elementu członkowskiego danych `m_CritSection` (typu `CCriticalSection` ) zadeklarowanego w klasie zasobów udostępnionych i `CSingleLock` obiekcie. Podjęto próbę synchronizacji zasobu udostępnionego (pochodzącego z `CWinThread` ) przez utworzenie `CSingleLock` obiektu przy użyciu adresu `m_CritSection` obiektu. Podjęto próbę zablokowania zasobu i, po uzyskaniu, pracy wykonywanej w obiekcie udostępnionym. Po zakończeniu pracy zasób jest odblokowany z wywołaniem do `Unlock` .

```cpp
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection`, w przeciwieństwie do innych klas synchronizacji MFC, nie ma opcji żądania blokady z limitem czasu. Okres oczekiwania dla wątku, który ma zostać zwolniony, jest nieskończony.

Wadą tego podejścia jest to, że klasa będzie nieco wolniej niż ta sama klasa bez dodanych obiektów synchronizacji. Ponadto, jeśli istnieje szansa, że więcej niż jeden wątek może usunąć obiekt, scalone podejście może nie być zawsze wykonywane. W takiej sytuacji lepiej jest zachować osobne obiekty synchronizacji.

Aby uzyskać informacje o określaniu, której klasy synchronizacji użyć w różnych sytuacjach, zobacz [wielowątkowość: Kiedy używać klas synchronizacji](multithreading-when-to-use-the-synchronization-classes.md). Aby uzyskać więcej informacji na temat synchronizacji, zobacz [Synchronizacja](/windows/win32/Sync/synchronization) w Windows SDK. Aby uzyskać więcej informacji na temat obsługi wielowątkowości w MFC, zobacz [wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Zobacz też

[Wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md)
