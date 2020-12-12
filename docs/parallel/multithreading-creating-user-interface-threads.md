---
description: 'Dowiedz się więcej na temat: Wielowątkowość: Tworzenie wątków MFC User-Interface'
title: 'Wielowątkowość: Tworzenie wątków MFC User-Interface'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
ms.openlocfilehash: bb3e388918f8881fbdd1968ef953da3067904350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149971"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>Wielowątkowość: Tworzenie wątków MFC User-Interface

Wątek interfejsu użytkownika jest często używany do obsługi danych wejściowych użytkownika i reagowania na zdarzenia użytkownika niezależnie od wątków wykonujących inne fragmenty aplikacji. Główny wątek aplikacji (podany w `CWinApp` klasie pochodnej) został już utworzony i uruchomiony. W tym temacie opisano kroki niezbędne do utworzenia dodatkowych wątków interfejsu użytkownika.

Pierwsza czynność, którą należy wykonać podczas tworzenia wątku interfejsu użytkownika, jest pochodną klasy z [CWinThread](../mfc/reference/cwinthread-class.md). Należy zadeklarować i zaimplementować tę klasę przy użyciu [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) i [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) makr. Ta klasa musi przesłaniać niektóre funkcje i może przesłonić inne. Te funkcje i informacje, które należy wykonać, zostały przedstawione w poniższej tabeli.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Funkcje do przesłonięcia podczas tworzenia wątku User-Interface

|Funkcja|Przeznaczenie|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|Wykonaj czyszczenie, gdy wątek zostanie przerwany. Zwykle zastępowane.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|Wykonaj inicjalizację wystąpienia wątku. Musi zostać zastąpiony.|
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|Wykonaj przetwarzanie w czasie bezczynności dla określonego wątku. Zwykle nie są zastępowane.|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|Filtrowanie komunikatów przed ich wysłaniem do `TranslateMessage` i `DispatchMessage` . Zwykle nie są zastępowane.|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|Przechwycenie nieobsłużonych wyjątków zgłoszonych przez komunikaty i procedury obsługi poleceń wątku. Zwykle nie są zastępowane.|
|[Uruchom](../mfc/reference/cwinthread-class.md#run)|Funkcja kontrolowania dla wątku. Zawiera pompę komunikatów. Rzadko zastępowane.|

MFC udostępnia dwie wersje `AfxBeginThread` przeciążania parametrów: jeden, który może tworzyć tylko wątki robocze i jeden, który może tworzyć wątki interfejsu użytkownika lub wątki robocze. Aby uruchomić wątek interfejsu użytkownika, wywołaj drugie Przeciążenie [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), podając następujące informacje:

- [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) klasy, z której pochodzą `CWinThread` .

- Obowiązkowe Żądany poziom priorytetu. Wartość domyślna to normalny priorytet. Aby uzyskać więcej informacji na temat dostępnych poziomów priorytetów, zobacz [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) w Windows SDK.

- Obowiązkowe Żądany rozmiar stosu dla wątku. Wartość domyślna to ten sam stos rozmiaru co wątek tworzenia.

- Obowiązkowe CREATE_SUSPENDED, jeśli chcesz, aby wątek został utworzony w stanie wstrzymania. Wartość domyślna to 0 lub Uruchom wątek normalnie.

- Obowiązkowe Wymagane atrybuty zabezpieczeń. Wartość domyślna to ten sam dostęp co wątek nadrzędny. Aby uzyskać więcej informacji na temat formatu informacji o zabezpieczeniach, zobacz [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) w Windows SDK.

`AfxBeginThread` wykonuje większość pracy. Tworzy nowy obiekt klasy, inicjuje go przy użyciu dostarczonych informacji i wywołuje [CWinThread:: Onthread](../mfc/reference/cwinthread-class.md#createthread) , aby rozpocząć wykonywanie wątku. Kontrole są wykonywane w ramach procedury, aby upewnić się, że wszystkie obiekty są prawidłowo nieprzypisane, jeśli jakakolwiek część procesu tworzenia nie powiedzie się.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Wielowątkowość: przerywanie wątków](multithreading-terminating-threads.md)

- [Wielowątkowość: Tworzenie wątków roboczych](multithreading-creating-worker-threads.md)

- [Procesy i wątki](/windows/win32/ProcThread/processes-and-threads)

## <a name="see-also"></a>Zobacz też

[Wielowątkowość z C++ i MFC](multithreading-with-cpp-and-mfc.md)
