---
description: 'Dowiedz się więcej na temat: Harmonogram zadań (środowisko uruchomieniowe współbieżności)'
title: Harmonogram zadań (współbieżność środowiska wykonawczego)
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription [Concurrency Runtime]
- task scheduler [Concurrency Runtime], oversubscription
- schedule groups [Concurrency Runtime]
- task scheduler [Concurrency Runtime], lightweight tasks
- task scheduler [Concurrency Runtime]
- lightweight tasks [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler policies
- task scheduler [Concurrency Runtime], schedule groups
- wait function [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler instances
- scheduler instances [Concurrency Runtime]
- scheduler policies [Concurrency Runtime]
- task scheduler [Concurrency Runtime], wait function
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
ms.openlocfilehash: db52b6714f5bdb96cb33aeea1bce1d92f5d5d4a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271385"
---
# <a name="task-scheduler-concurrency-runtime"></a>Harmonogram zadań (współbieżność środowiska wykonawczego)

W tematach w tej części dokumentacji opisano ważne funkcje Harmonogram zadań środowisko uruchomieniowe współbieżności. Harmonogram zadań jest przydatne, gdy chcesz dostosować wydajność istniejącego kodu, który korzysta z środowisko uruchomieniowe współbieżności.

> [!IMPORTANT]
> Harmonogram zadań nie jest dostępna w aplikacji platforma uniwersalna systemu Windows (platformy UWP). Aby uzyskać więcej informacji, zobacz [Tworzenie operacji asynchronicznych w języku C++ dla aplikacji platformy UWP](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).
>
> W programie Visual Studio 2015 i nowszych, Klasa [concurrency:: Task](../../parallel/concrt/reference/task-class.md) i powiązane typy w ppltasks. h używają puli wątków systemu Windows jako harmonogramu. Ten temat nie ma już zastosowania do typów, które są zdefiniowane w ppltasks. h. Algorytmy równoległe, takie jak parallel_for, nadal używają środowisko uruchomieniowe współbieżności jako harmonogramu domyślnego.

> [!TIP]
> Środowisko uruchomieniowe współbieżności udostępnia domyślny harmonogram i dlatego nie jest konieczne tworzenie go w aplikacji. Ponieważ Harmonogram zadań ułatwia dostosowanie wydajności aplikacji, zalecamy rozpoczęcie od [biblioteki równoległych wzorców (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) lub [biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md) , jeśli są one nowe dla środowisko uruchomieniowe współbieżności.

Harmonogram zadań planuje i koordynuje zadania w czasie wykonywania. *Zadanie* jest jednostką pracy, która wykonuje określone zadanie. Zadanie można zwykle uruchomić równolegle z innymi zadaniami. Zadania wykonywane przez elementy grupy zadań, algorytmy równoległe i agenci asynchroniczni to wszystkie przykłady zadań.

Harmonogram zadań zarządza szczegółami związanymi z wydajnym planowaniem zadań na komputerach, które mają wiele zasobów obliczeniowych. Harmonogram zadań używa również najnowszych funkcji bazowego systemu operacyjnego. W związku z tym aplikacje, które używają środowisko uruchomieniowe współbieżności, są automatycznie skalowane i ulepszane na sprzęcie, który ma rozszerzone możliwości.

[Porównanie z innymi modelami współbieżności](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md) opisuje różnice między mechanizmami planowania z przeznaczeniem i współdziałaniem. W Harmonogram zadań są stosowane wspólne planowanie i algorytm kradzieży pracy wraz z zaplanowanym harmonogramem systemu operacyjnego w celu osiągnięcia maksymalnego użycia zasobów przetwarzania.

Środowisko uruchomieniowe współbieżności udostępnia domyślny harmonogram, dzięki czemu nie trzeba zarządzać szczegółami infrastruktury. W związku z tym zazwyczaj nie używaj Harmonogram zadań bezpośrednio. Aby jednak spełnić wymagania dotyczące jakości aplikacji, można użyć Harmonogram zadań w celu zapewnienia własnych zasad planowania lub kojarzenia harmonogramów z określonymi zadaniami. Załóżmy na przykład, że masz równoległą procedurę sortowania, która nie jest skalowana poza cztery procesory. Za pomocą *zasad usługi Scheduler* można utworzyć harmonogram, który generuje nie więcej niż cztery współbieżne zadania. Uruchomienie procedury sortowania w tym harmonogramie umożliwia innym aktywnym harmonogramom korzystanie z pozostałych zasobów przetwarzania.

## <a name="related-topics"></a>Tematy pokrewne

|Tytuł|Opis|
|-----------|-----------------|
|[Wystąpienia harmonogramu](../../parallel/concrt/scheduler-instances.md)|Opisuje wystąpienia harmonogramu i sposób używania `concurrency::Scheduler` `concurrency::CurrentScheduler` klas i do zarządzania nimi. Użyj wystąpień usługi Scheduler, jeśli chcesz skojarzyć jawne zasady planowania z określonymi typami obciążeń.|
|[Zasady usługi Scheduler](../../parallel/concrt/scheduler-policies.md)|Opisuje rolę zasad usługi Scheduler. Zasady usługi Scheduler umożliwiają sterowanie strategią używaną przez harmonogram podczas zarządzania zadaniami.|
|[Zaplanuj grupy](../../parallel/concrt/schedule-groups.md)|Opisuje rolę grup harmonogramów. Używaj grup zaplanowanych, gdy wymagasz wysokiego stopnia zawieszania między zadaniami, na przykład gdy grupa powiązanych zadań korzysta z wykonywania w tym samym węźle procesora.|
|[Zadania lekkie](../../parallel/concrt/lightweight-tasks.md)|Opisuje rolę uproszczonych zadań. Uproszczone zadania są przydatne podczas dostosowywania istniejącego kodu do korzystania z funkcji planowania środowisko uruchomieniowe współbieżności.|
|[Konteksty](../../parallel/concrt/contexts.md)|Opisuje rolę kontekstów, `concurrency::wait` funkcję i `concurrency::Context` klasę. Użyj tej funkcji, jeśli chcesz kontrolować, gdy konteksty blokują, odblokują i implikują, lub kiedy mają być włączane nadmiarowe w aplikacji.|
|[Funkcje zarządzania pamięcią](../../parallel/concrt/memory-management-functions.md)|Opisuje `concurrency::Alloc` funkcje i `concurrency::Free` . Te funkcje mogą zwiększyć wydajność pamięci przez przydzielenie i zwolnienie pamięci w sposób współbieżny.|
|[Porównywanie z innymi modelami współbieżności](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|Opisuje różnice między mechanizmami planowania z przeznaczeniem i współdziałaniem.|
|[Biblioteka równoległych wzorców (PLL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Opisuje sposób używania różnych równoległych wzorców, na przykład algorytmów równoległych, w aplikacjach.|
|[Biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md)|Opisuje, jak używać agentów asynchronicznych w aplikacjach.|
|[Współbieżność środowiska wykonawczego](../../parallel/concrt/concurrency-runtime.md)|Opisuje środowisko uruchomieniowe współbieżności, które upraszczają programowanie równoległe i zawiera linki do powiązanych tematów.|
