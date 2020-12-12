---
description: 'Dowiedz się więcej: Kiedy używać klas synchronizacji MFC'
title: 'Wielowątkowość: Kiedy używać klas synchronizacji MFC'
ms.date: 08/27/2018
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
ms.openlocfilehash: 02776bc61ed702ee81ce0f7373dd442a9fc3d446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149854"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>Wielowątkowość: Kiedy używać klas synchronizacji MFC

Klasy wielowątkowe dostarczone z MFC dzielą się na dwie kategorie: obiekty synchronizacji ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [CCriticalSection](../mfc/reference/ccriticalsection-class.md)i [CEvent](../mfc/reference/cevent-class.md)) oraz obiekty dostępu do synchronizacji ([CMultiLock](../mfc/reference/cmultilock-class.md) i [CSingleLock](../mfc/reference/csinglelock-class.md)).

Klasy synchronizacji są używane, gdy dostęp do zasobu musi być kontrolowany, aby zapewnić integralność zasobu. Klasy dostępu do synchronizacji są używane do uzyskiwania dostępu do tych kontrolowanych zasobów. W tym temacie opisano, kiedy należy używać każdej klasy.

Aby określić, której klasy synchronizacji należy użyć, zażądaj następującej serii pytań:

1. Czy aplikacja musi oczekiwać przed uzyskaniem dostępu do zasobu (na przykład należy odebrać dane z portu komunikacyjnego, zanim będzie można go zapisać w pliku)?

   Jeśli tak, użyj `CEvent` .

2. Może jednocześnie uzyskać dostęp do tego zasobu z więcej niż jednego wątku w tej samej aplikacji (na przykład aplikacja umożliwia maksymalnie pięć okien z widokami w tym samym dokumencie)?

   Jeśli tak, użyj `CSemaphore` .

3. Czy więcej niż jedna aplikacja korzysta z tego zasobu (na przykład zasób znajduje się w bibliotece DLL)?

   Jeśli tak, użyj `CMutex` .

   Jeśli nie, użyj `CCriticalSection` .

`CSyncObject` nie jest nigdy używane bezpośrednio. Jest klasą bazową dla innych czterech klas synchronizacji.

## <a name="example-1-using-three-synchronization-classes"></a>Przykład 1: korzystanie z trzech klas synchronizacji

Na przykład Utwórz aplikację, która utrzymuje połączoną listę kont. Ta aplikacja umożliwia przeanalizowanie maksymalnie trzech kont w oddzielnych oknach, ale tylko jeden z nich można zaktualizować w określonym czasie. W przypadku zaktualizowania konta zaktualizowane dane są wysyłane przez sieć do archiwum danych.

Ta przykładowa aplikacja używa wszystkich trzech typów klas synchronizacji. Ponieważ pozwala na przeanalizowanie maksymalnie trzech kont, służy on `CSemaphore` do ograniczania dostępu do trzech obiektów widoku. Podczas próby wyświetlenia czwartego konta następuje odczekanie, aż jeden z trzech pierwszych okien zostanie zamknięty lub zakończy się niepowodzeniem. Gdy konto jest aktualizowane, aplikacja używa programu `CCriticalSection` w celu zapewnienia, że tylko jedno konto jest aktualizowane jednocześnie. Po pomyślnym zakończeniu aktualizacji program sygnalizuje `CEvent` , że zwalnia wątek oczekujący na zasygnalizowanie zdarzenia. Ten wątek wysyła nowe dane do archiwum danych.

## <a name="example-2-using-synchronization-access-classes"></a>Przykład 2: używanie klas dostępu do synchronizacji

Wybór używanej klasy dostępu do synchronizacji jest jeszcze prostsze. Jeśli aplikacja jest objęta dostępem tylko do pojedynczego kontrolowanego zasobu, użyj `CSingleLock` . Jeśli potrzebuje dostępu do jednej z wielu kontrolowanych zasobów, użyj `CMultiLock` . W przykładzie 1 `CSingleLock` zostałaby użyta, ponieważ w każdym konkretnym czasie potrzeba tylko jednego zasobu.

Aby uzyskać informacje o sposobie używania klas synchronizacji, zobacz [wielowątkowość: jak używać klas synchronizacji](multithreading-how-to-use-the-synchronization-classes.md). Aby uzyskać informacje na temat synchronizacji, zobacz [Synchronizacja](/windows/win32/Sync/synchronization) w Windows SDK. Aby uzyskać informacje o obsłudze wielowątkowości w MFC, zobacz [wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md).

## <a name="see-also"></a>Zobacz też

[Wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md)
