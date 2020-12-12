---
description: 'Dowiedz się więcej o: funkcjach zarządzania pamięcią'
title: Funkcje zarządzania pamięcią
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: d75778f99294c1a177ac204bb0fb96c3ee84422c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205541"
---
# <a name="memory-management-functions"></a>Funkcje zarządzania pamięcią

W tym dokumencie opisano funkcje zarządzania pamięcią zapewniane przez środowisko uruchomieniowe współbieżności, które ułatwiają przydzielanie i zwalnianie pamięci w sposób współbieżny.

> [!TIP]
> Środowisko uruchomieniowe współbieżności udostępnia domyślny harmonogram i dlatego nie jest konieczne tworzenie go w aplikacji. Ponieważ Harmonogram zadań ułatwia dostosowanie wydajności aplikacji, zalecamy rozpoczęcie od [biblioteki równoległych wzorców (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) lub [biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md) , jeśli są one nowe dla środowisko uruchomieniowe współbieżności.

Środowisko uruchomieniowe współbieżności udostępnia dwie funkcje zarządzania pamięcią, które są zoptymalizowane pod kątem przydzielania i zwalniania bloków pamięci w sposób współbieżny. Funkcja [concurrency:: Alloc](reference/concurrency-namespace-functions.md#alloc) przypisuje blok pamięci przy użyciu określonego rozmiaru. Funkcja [concurrency:: Free](reference/concurrency-namespace-functions.md#free) zwalnia pamięć, która została przypisana przez program `Alloc` .

> [!NOTE]
> `Alloc`Funkcje i są `Free` zależne od siebie. Funkcji należy używać `Free` tylko w przypadku zwalniania pamięci przydzielonej przy użyciu `Alloc` funkcji. Ponadto przy użyciu `Alloc` funkcji w celu przydzielenia pamięci Użyj tylko funkcji, `Free` Aby zwolnić pamięć.

W `Alloc` `Free` przypadku przydzielania i zwalniania ustalonego zestawu rozmiarów alokacji z różnych wątków lub zadań należy używać funkcji i. Środowisko uruchomieniowe współbieżności pamięci podręcznej pamięć podręczna przydzielona ze sterty środowiska uruchomieniowego języka C. Środowisko uruchomieniowe współbieżności przechowuje osobną pamięć podręczną pamięci dla każdego działającego wątku; w związku z tym środowisko uruchomieniowe zarządza pamięcią bez użycia blokad lub barier pamięci. Aplikacja korzysta z `Alloc` funkcji i w `Free` przypadku, gdy dostęp do pamięci podręcznej jest częściej. Na przykład wątek, który często wywołuje jednocześnie `Alloc` i `Free` korzysta z więcej niż wątek, który głównie wywołuje `Alloc` lub `Free` .

> [!NOTE]
> W przypadku korzystania z tych funkcji zarządzania pamięcią, gdy aplikacja korzysta z dużej ilości pamięci, aplikacja może bezproblemowo wprowadzić warunek niskiej ilości pamięci niż oczekiwano. Ponieważ bloki pamięci buforowane przez jeden wątek nie są dostępne dla żadnego innego wątku, jeśli jeden wątek zawiera wiele pamięci, ta pamięć jest niedostępna.

## <a name="example"></a>Przykład

Przykład korzystający z `Alloc` `Free` funkcji i w celu zwiększenia wydajności pamięci można znaleźć w temacie [How to: use a Free (alokacja i bezpłatna) w celu zwiększenia wydajności pamięci](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

## <a name="see-also"></a>Zobacz też

[Harmonogram zadań](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Instrukcje: korzystanie z Alloc i Free w celu zwiększenia wydajności pamięci](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
