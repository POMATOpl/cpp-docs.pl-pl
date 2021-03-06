---
description: 'Dowiedz się więcej o: obsługa wielowątkowości dla starszego kodu (Visual C++)'
title: Obsługa wielowątkowości w przypadku starszego kodu (Visual C++)
ms.date: 08/27/2018
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
ms.openlocfilehash: a3b04fdde01e2576d37d41f2860526fcf5ba1691
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149906"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Obsługa wielowątkowości w przypadku starszego kodu (Visual C++)

Visual C++ umożliwia jednoczesne uruchamianie wielu współbieżnych wątków wykonywania. W przypadku wielowątkowości można wyłączać zadania w tle, zarządzać jednoczesnymi strumieniami danych wejściowych, zarządzać interfejsem użytkownika i wiele innych.

## <a name="in-this-section"></a>W tej sekcji

[Wielowątkowość z językiem C i podsystemem Win32](multithreading-with-c-and-win32.md)<br/>
Zapewnia obsługę tworzenia aplikacji wielowątkowej w systemie Microsoft Windows

[Wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md)<br/>
Opisuje procesy i wątki oraz to, co jest podejściem MFC do wielowątkowości.

[Wielowątkowość i ustawienia regionalne](multithreading-and-locales.md)<br/>
Omawia problemy, które powstają w przypadku korzystania z funkcji regionalnych biblioteki środowiska uruchomieniowego C i standardowej biblioteki języka C++ w aplikacji wielowątkowej.

## <a name="related-sections"></a>Sekcje pokrewne

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Reprezentuje wątek wykonywania w aplikacji.

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Opisuje czystą klasę wirtualną, która zapewnia funkcje wspólne dla obiektów synchronizacji w systemie Win32.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Reprezentuje semafor, który jest obiektem synchronizacji umożliwiającym ograniczoną liczbę wątków w jednym lub wielu procesach uzyskiwania dostępu do zasobu.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Reprezentuje element mutex, który jest obiektem synchronizacji umożliwiającym jednemu wątkowi wyłączny dostęp do zasobu.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Reprezentuje sekcję krytyczną, która jest obiektem synchronizacji umożliwiającym jednemu wątkowi w danym momencie uzyskanie dostępu do zasobu lub sekcji kodu.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Reprezentuje zdarzenie, które jest obiektem synchronizacji umożliwiającym jednemu wątkowi powiadamianie innego o wystąpieniu zdarzenia.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
Reprezentuje mechanizm kontroli dostępu używany do kontrolowania dostępu do zasobów w programie wielowątkowym.

[CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
Reprezentuje mechanizm kontroli dostępu używany do kontrolowania dostępu do zasobu w programie wielowątkowym.
