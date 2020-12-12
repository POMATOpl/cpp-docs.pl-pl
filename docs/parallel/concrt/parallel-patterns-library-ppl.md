---
description: Dowiedz się więcej o bibliotece równoległych wzorców (PPL)
title: Biblioteka równoległych wzorców (PLL)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
ms.openlocfilehash: ea5719e8ebaacf8f181678ef7af8aae9c900fbe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172352"
---
# <a name="parallel-patterns-library-ppl"></a>Biblioteka równoległych wzorców (PLL)

Biblioteka równoległych wzorców (PPL) zapewnia bezwzględny model programistyczny, który promuje skalowalność i łatwość używania do tworzenia współbieżnych aplikacji. PPL opiera się na składnikach planowania i zarządzania zasobami środowisko uruchomieniowe współbieżności. Podnosi poziom abstrakcji między kodem aplikacji a podstawowym mechanizmem wątkowości przez dostarczanie ogólnych, bezpiecznych algorytmów i kontenerów, które działają równolegle z danymi. PPL umożliwia również opracowywanie aplikacji, które są skalowane, dostarczając alternatywy do udostępnionego stanu.

PPL zapewnia następujące funkcje:

- *Równoległość zadań*: mechanizm, który działa na początku puli wątków systemu Windows w celu wykonywania równolegle kilku elementów roboczych (zadań)

- *Algorytmy równoległe*: algorytmy ogólne, które działają na podstawie środowisko uruchomieniowe współbieżności, aby wykonywać równolegle kolekcje danych

- *Równoległe kontenery i obiekty*: typy kontenerów ogólnych, które zapewniają bezpieczny współbieżny dostęp do ich elementów

## <a name="example"></a>Przykład

PPL zapewnia model programowania, który jest podobny do standardowej biblioteki języka C++. Poniższy przykład ilustruje wiele funkcji PPL. Oblicza kilka Fibonacci numerów seryjnych i równolegle. Oba obliczenia działają na obiekcie [std:: Array](../../standard-library/array-class-stl.md) . W przykładzie pokazano również drukowanie do konsoli programu czas wymagany do wykonania obu obliczeń.

Wersja szeregowa używa algorytmu standardowej biblioteki C++ [:: for_each](../../standard-library/algorithm-functions.md#for_each) , aby przepływać tablicę i przechowywał wyniki w obiekcie [wektora std:: Vector](../../standard-library/vector-class.md) . Wersja równoległa wykonuje to samo zadanie, ale używa algorytmu PPL [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) i zapisuje wyniki w obiekcie [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) . `concurrent_vector`Klasa umożliwia każdej iteracji pętli równoczesne Dodawanie elementów bez wymagania synchronizacji dostępu do zapisu w kontenerze.

Ze względu `parallel_for_each` na to, że równoległa wersja tego przykładu musi posortować `concurrent_vector` obiekt, aby generować te same wyniki co wersja szeregowa.

Należy zauważyć, że w przykładzie zastosowano metodę algorytmie w celu obliczenia wartości Fibonacci; Jednak ta metoda ilustruje, jak środowisko uruchomieniowe współbieżności może poprawić wydajność długich obliczeń.

[!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
serial time: 9250 ms
parallel time: 5726 ms

fib(24): 46368
fib(26): 121393
fib(41): 165580141
fib(42): 267914296
```

Każda iteracja pętli wymaga innego czasu na zakończenie. Wydajność `parallel_for_each` jest ograniczona przez operację, która kończy się ostatnią. W związku z tym nie należy oczekiwać liniowych ulepszeń wydajności między wersjami Standard i Parallel tego przykładu.

## <a name="related-topics"></a>Tematy pokrewne

|Tytuł|Opis|
|-----------|-----------------|
|[Równoległość zadań](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Opisuje rolę zadań i grup zadań w PPL.|
|[Algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md)|Opisuje sposób korzystania z algorytmów równoległych, takich jak `parallel_for` i `parallel_for_each` .|
|[Równoległe kontenery i obiekty](../../parallel/concrt/parallel-containers-and-objects.md)|Opisuje różne kontenery równoległe i obiekty, które są dostarczane przez PPL.|
|[Anulowanie w PPL](cancellation-in-the-ppl.md)|Wyjaśnia, jak anulować pracę wykonywaną przez algorytm równoległy.|
|[Współbieżność środowiska wykonawczego](../../parallel/concrt/concurrency-runtime.md)|Opisuje środowisko uruchomieniowe współbieżności, które upraszczają programowanie równoległe i zawiera linki do powiązanych tematów.|
