---
title: 'Instrukcje: Tworzenie zadania kończonego po opóźnieniu'
description: Utwórz zadanie, które kończy się po opóźnieniu przy użyciu biblioteki PPL ConcRT.
ms.date: 10/19/2020
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 694b6190a7ec60043a5674e920dc54e6e7bf0eb6
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274562"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Instrukcje: Tworzenie zadania kończonego po opóźnieniu

Ten przykład pokazuje, jak używać klas,,,, [`concurrency::task`](../../parallel/concrt/reference/task-class.md) [`concurrency::cancellation_token_source`](../../parallel/concrt/reference/cancellation-token-source-class.md) [`concurrency::cancellation_token`](../../parallel/concrt/reference/cancellation-token-class.md) [`concurrency::task_completion_event`](../../parallel/concrt/reference/task-completion-event-class.md) [`concurrency::timer`](../../parallel/concrt/reference/timer-class.md) i [`concurrency::call`](../../parallel/concrt/reference/call-class.md) do tworzenia zadania, które kończy się po opóźnieniu. Za pomocą tej metody można kompilować pętle, które okresowo sonduje dane. Można także wprowadzić limity czasu, opóźnić obsługę danych wejściowych użytkownika przez określony czas i tak dalej.

## <a name="example-complete_after-and-cancel_after_timeout-functions"></a>Przykład: complete_after i funkcje cancel_after_timeout

W poniższym przykładzie przedstawiono `complete_after` funkcje i `cancel_after_timeout` . `complete_after`Funkcja tworzy `task` obiekt, który kończy się po określonym opóźnieniu. Używa `timer` obiektu i `call` obiektu do ustawienia `task_completion_event` obiektu po określonym opóźnieniu. Korzystając z `task_completion_event` klasy, można zdefiniować zadanie, które kończy się po wątku lub inne zadanie sygnalizuje, że wartość jest dostępna. Po ustawieniu zdarzenia zadania odbiornika są wykonywane, a ich kontynuacje są zaplanowane do uruchomienia.

> [!TIP]
> Aby uzyskać więcej informacji na `timer` temat `call` klas i, które są częścią biblioteki agentów asynchronicznych, zobacz [asynchroniczne bloki komunikatów](../../parallel/concrt/asynchronous-message-blocks.md).

`cancel_after_timeout`Funkcja kompiluje funkcję w `complete_after` celu anulowania zadania, jeśli zadanie nie zostanie zakończone przed upływem danego limitu czasu. `cancel_after_timeout`Funkcja tworzy dwa zadania. Pierwsze zadanie wskazuje na powodzenie i zakończenie po zakończeniu podanego zadania. Drugie zadanie wskazuje błąd i kończy się po określonym limicie czasu. `cancel_after_timeout`Funkcja tworzy zadanie kontynuacji, które jest uruchamiane po zakończeniu zadania sukces lub niepowodzenie. Jeśli zadanie niepowodzenia zakończy się najpierw, kontynuacja spowoduje anulowanie źródła tokenu w celu anulowania zadania ogólnego.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example-compute-count-of-prime-numbers"></a>Przykład: liczba obliczeń liczby pierwszych

Poniższy przykład oblicza liczbę liczb pierwszych z zakresu [0, 100000] wiele razy. Operacja kończy się niepowodzeniem, jeśli nie zostanie zakończona w danym limicie czasu. `count_primes`Funkcja pokazuje, jak używać `cancel_after_timeout` funkcji. Zlicza on liczbę elementów w danym zakresie i kończy się niepowodzeniem, jeśli zadanie nie zostało ukończone w danym czasie. `wmain`Funkcja wywołuje `count_primes` funkcję wielokrotnie. Za każdym razem ilość czasu jest mniejsza. Program kończy pracę po zakończeniu operacji w bieżącym limicie czasu.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

Gdy ta technika jest używana do anulowania zadań po opóźnieniu, wszelkie zadania, które nie zostały uruchomione, nie będą uruchamiane po anulowaniu całego zadania. Jednak ważne jest, aby w przypadku długotrwałych zadań szybko odpowiedzieć na anulowanie. Aby uzyskać więcej informacji o anulowaniu zadania, zobacz [Anulowanie w PPL](cancellation-in-the-ppl.md).

## <a name="complete-code-example"></a>Pełny przykład kodu

Oto kompletny kod dla tego przykładu:

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `task-delay.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

**cl.exe/EHsc Task-Delay. cpp**

## <a name="see-also"></a>Zobacz też

[Równoległość zadań](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Task — Klasa (środowisko uruchomieniowe współbieżności)](../../parallel/concrt/reference/task-class.md)<br/>
[Klasa cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[Klasa cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[Klasa task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[Timer — Klasa](../../parallel/concrt/reference/timer-class.md)<br/>
[Call, Klasa](../../parallel/concrt/reference/call-class.md)<br/>
[Bloki komunikatów asynchronicznych](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Anulowanie w PPL](cancellation-in-the-ppl.md)
