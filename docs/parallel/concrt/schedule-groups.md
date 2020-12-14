---
description: 'Dowiedz się więcej o: grupy harmonogramu'
title: Grupy harmonogramu
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
ms.openlocfilehash: bee4f20ae58f94ddad93770232028df7b82dd39e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188069"
---
# <a name="schedule-groups"></a>Grupy harmonogramu

W tym dokumencie opisano role grup harmonogramu w środowisko uruchomieniowe współbieżności. *Grupy harmonogramu* skoligaconyą lub grupowo powiązane zadania. Każdy harmonogram ma co najmniej jedną grupę harmonogramów. Używaj grup zaplanowanych, gdy wymagasz wysokiego stopnia zawieszania między zadaniami, na przykład gdy grupa powiązanych zadań korzysta z wykonywania w tym samym węźle procesora. Należy również użyć wystąpień usługi Scheduler, gdy aplikacja ma określone wymagania dotyczące jakości, na przykład, gdy chcesz ograniczyć ilość zasobów przetwarzania przyznanych do zestawu zadań. Aby uzyskać więcej informacji o wystąpieniach harmonogramu, zobacz [wystąpienia usługi Scheduler](../../parallel/concrt/scheduler-instances.md).

> [!TIP]
> Środowisko uruchomieniowe współbieżności udostępnia domyślny harmonogram i dlatego nie jest konieczne tworzenie go w aplikacji. Ponieważ Harmonogram zadań ułatwia dostosowanie wydajności aplikacji, zalecamy rozpoczęcie od [biblioteki równoległych wzorców (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) lub [biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md) , jeśli są one nowe dla środowisko uruchomieniowe współbieżności.

Każdy `Scheduler` obiekt ma domyślną grupę harmonogramów dla każdego węzła planowania. *Węzeł planowania* jest mapowany do podstawowej topologii systemu. Środowisko uruchomieniowe tworzy jeden węzeł planowania dla każdego pakietu procesora lub węzła non-uniform Memory Architecture (NUMA), niezależnie od liczby. Jeśli zadanie nie zostanie jawnie skojarzone z grupą harmonogramów, harmonogram wybierze grupę, do której ma zostać dodane zadanie.

`SchedulingProtocol`Zasady harmonogramu mają wpływ na kolejność wykonywania zadań w ramach poszczególnych grup harmonogramów. Gdy `SchedulingProtocol` jest ustawiona na `EnhanceScheduleGroupLocality` (jest to ustawienie domyślne), harmonogram zadań wybiera następne zadanie z grupy harmonogramów, nad którym pracuje, gdy bieżące zadanie zakończy się lub spółdzielnie. Harmonogram zadań przeszukuje bieżącą grupę harmonogramów pracy przed przejściem do następnej dostępnej grupy. Z drugiej strony, gdy `SchedulingProtocol` jest ustawiona na `EnhanceForwardProgress` , harmonogram przechodzi do następnej grupy harmonogramów po zakończeniu każdego zadania lub jego uzyskaniu. Aby zapoznać się z przykładem porównującym te zasady, zobacz [jak: używanie grup harmonogramu do wywierania wpływu na kolejność wykonywania](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

Środowisko uruchomieniowe używa klasy [concurrency:: Schedule](../../parallel/concrt/reference/schedulegroup-class.md) Group do reprezentowania grup harmonogramów. Aby utworzyć `ScheduleGroup` obiekt, wywołaj metodę [concurrency:: CurrentScheduler:: SetSchedule](reference/currentscheduler-class.md#createschedulegroup) lub [concurrency:: Scheduler::](reference/scheduler-class.md#createschedulegroup) . Środowisko uruchomieniowe używa mechanizmu zliczania odwołań do kontrolowania okresu istnienia `ScheduleGroup` obiektów, podobnie jak w przypadku `Scheduler` obiektów. Podczas tworzenia `ScheduleGroup` obiektu środowisko uruchomieniowe ustawia licznik odwołania na jeden. Metoda [concurrency:: Schedule](reference/schedulegroup-class.md#reference) ;: Reference zwiększa licznik odwołań o jeden. [Concurrency:: scheduleing:: Release](reference/schedulegroup-class.md#release) Metoda zmniejsza licznik odwołań o jeden.

Wiele typów w środowisko uruchomieniowe współbieżności umożliwia skojarzenie obiektu z grupą harmonogramów. Na przykład Klasa [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) i blok komunikatów, takie jak [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: join](../../parallel/concrt/reference/join-class.md)i concurrency::[Timer](reference/timer-class.md), zapewniają przeciążone wersje konstruktora, który przyjmuje `ScheduleGroup` obiekt. Środowisko uruchomieniowe używa `Scheduler` obiektu, który jest skojarzony z tym `ScheduleGroup` obiektem w celu zaplanowania zadania.

Można również użyć metody [concurrency:: Schedule:: ScheduleTask —](reference/schedulegroup-class.md#scheduletask) , aby zaplanować lekkie zadanie. Aby uzyskać więcej informacji na temat uproszczonych zadań, zobacz [zadania uproszczone](../../parallel/concrt/lightweight-tasks.md).

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem korzystającym z grup harmonogramu do kontrolowania kolejności wykonywania zadań, zobacz [How to: use Groups Schedule by mieć wpływ na kolejność wykonywania](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="see-also"></a>Zobacz też

[Harmonogram zadań](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Wystąpienia harmonogramu](../../parallel/concrt/scheduler-instances.md)<br/>
[Instrukcje: używanie grup harmonogramu do wywierania wpływu na kolejność wykonywania](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)
