---
description: 'Dowiedz się więcej na temat: jak określić określone zasady harmonogramu'
title: 'Porady: określanie specjalnych zasad harmonogramu'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: c4aeeea04d69613ef3eb80f36863b16530e18e37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197260"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Porady: określanie specjalnych zasad harmonogramu

Zasady usługi Scheduler umożliwiają sterowanie strategią używaną przez harmonogram podczas zarządzania zadaniami. W tym temacie pokazano, jak za pomocą zasad harmonogramu zwiększyć priorytet wątku zadania, które drukuje wskaźnik postępu w konsoli programu.

Aby zapoznać się z przykładem korzystającym z niestandardowych zasad harmonogramu razem z agentami asynchronicznymi, zobacz [How to: Create Agents, który korzysta z określonych zasad usługi Scheduler](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="example"></a>Przykład

Poniższy przykład wykonuje równolegle dwa zadania. Pierwsze zadanie oblicza n-<sup>ty</sup> numer Fibonacci. Drugie zadanie drukuje wskaźnik postępu do konsoli.

Pierwsze zadanie używa dekompozycji cyklicznej w celu obliczenia numeru Fibonacci. Oznacza to, że każde zadanie rekurencyjnie tworzy podzadania w celu obliczenia całkowitego wyniku. Zadanie, które korzysta z dekompozycji cyklicznej, może korzystać ze wszystkich dostępnych zasobów, a tym samym zablokować dostęp inne zadania. W tym przykładzie zadanie, które drukuje wskaźnik postępu, może nie uzyskać czasu dostępu do zasobów obliczeniowych.

Aby zapewnić zadanie, które drukuje komunikat o postępie z uczciwym dostępem do zasobów obliczeniowych, w tym przykładzie są używane kroki opisane w artykule [How to: Manage a Scheduler instance](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) to Create a Scheduler Policy instance. Zasady niestandardowe określają priorytet wątku, który jest klasą o najwyższym priorytecie.

W tym przykładzie zastosowano klasy [concurrency:: Call](../../parallel/concrt/reference/call-class.md) i [concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) do drukowania wskaźnika postępu. Te klasy mają wersje konstruktorów, które przyjmują odwołanie do obiektu [concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) , który je planuje. W przykładzie używa się domyślnego harmonogramu do zaplanowania zadania, które oblicza numer Fibonacci i wystąpienie harmonogramu, aby zaplanować zadanie, które drukuje wskaźnik postępu.

Aby zilustrować zalety korzystania z harmonogramu, który ma zasady niestandardowe, ten przykład wykonuje ogólne zadanie dwa razy. W przykładzie najpierw jest planowane zaplanowanie obu zadań przy użyciu domyślnego harmonogramu. W przykładzie zostanie użyty domyślny harmonogram w celu zaplanowania pierwszego zadania i harmonogram, który ma zasady niestandardowe, aby zaplanować drugie zadanie.

[!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]

Ten przykład generuje następujące dane wyjściowe.

```Output
Default scheduler:
...........................................................................done
Scheduler that has a custom policy:
...........................................................................done
```

Mimo że oba zestawy zadań tworzą ten sam wynik, wersja, która używa zasad niestandardowych, umożliwia zadanie, które drukuje wskaźnik postępu do uruchamiania z podwyższonym priorytetem, dzięki czemu będzie bardziej reagować.

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `scheduler-policy.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Scheduler-Policy. cpp**

## <a name="see-also"></a>Zobacz też

[Zasady usługi Scheduler](../../parallel/concrt/scheduler-policies.md)<br/>
[Instrukcje: Zarządzanie wystąpieniem harmonogramu](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[Instrukcje: Tworzenie agentów korzystających z określonych zasad usługi Scheduler](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
