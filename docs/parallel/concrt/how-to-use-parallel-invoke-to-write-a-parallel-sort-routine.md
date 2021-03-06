---
description: 'Dowiedz się więcej na temat: jak używać parallel_invoke, aby napisać równoległą procedurę sortowania'
title: 'Porady: używanie parallel_invoke do napisania procedury sortowania równoległego'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 4146bed939e265f611d79c465681c10ef28a1ebe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205671"
---
# <a name="how-to-use-parallel_invoke-to-write-a-parallel-sort-routine"></a>Porady: używanie parallel_invoke do napisania procedury sortowania równoległego

W tym dokumencie opisano sposób użycia algorytmu [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) w celu zwiększenia wydajności algorytmu sortowania bitonicznego. Algorytm sortowania bitonicznego rekursywnie dzieli sekwencję wejściową na mniejsze posortowane partycje. Algorytm sortowania bitonicznego można uruchomić równolegle, ponieważ każda operacja partycji jest niezależna od wszystkich innych operacji.

Chociaż sortowanie bitonicznego jest przykładem *sieci sortowania* , która sortuje wszystkie kombinacje sekwencji wejściowych, w tym przykładzie są sortowane sekwencje, których długość jest potęgą dwóch.

> [!NOTE]
> W tym przykładzie zastosowano równoległą procedurę sortowania dla ilustracji. Można również użyć wbudowanych algorytmów sortowania, które zapewnia PPL: [concurrency::p arallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::p arallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)i [concurrency::p arallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Aby uzyskać więcej informacji, zobacz [algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md).

## <a name="sections"></a><a name="top"></a> Poszczególne

W tym dokumencie opisano następujące zadania:

- [Wykonywanie sortowania bitonicznego w sposób szeregowy](#serial)

- [Używanie parallel_invoke do równoległego sortowania bitonicznego](#parallel)

## <a name="performing-bitonic-sort-serially"></a><a name="serial"></a> Wykonywanie sortowania bitonicznego w sposób szeregowy

Poniższy przykład pokazuje wersję seryjną algorytmu sortowania bitonicznego. `bitonic_sort`Funkcja dzieli sekwencję na dwie partycje, sortuje te partycje w odwrotnych kierunkach, a następnie scala wyniki. Ta funkcja wywołuje dwa razy cyklicznie, aby posortować każdą partycję.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Top](#top)]

## <a name="using-parallel_invoke-to-perform-bitonic-sort-in-parallel"></a><a name="parallel"></a> Używanie parallel_invoke do równoległego sortowania bitonicznego

W tej sekcji opisano, jak używać `parallel_invoke` algorytmu do równoległego wykonywania algorytmu sortowania bitonicznego.

### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Aby wykonać algorytm bitonicznego sortowania równolegle

1. Dodaj `#include` dyrektywę dla pliku nagłówkowego PPL. h.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Dodaj **`using`** dyrektywę dla `concurrency` przestrzeni nazw.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Utwórz nową funkcję o nazwie `parallel_bitonic_mege` , która używa `parallel_invoke` algorytmu do scalania sekwencji równolegle, jeśli istnieje wystarczająca ilość pracy do wykonania. W przeciwnym razie Wywołaj, `bitonic_merge` Aby scalić sekwencje sekwencyjnie.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Wykonaj proces podobny do przedstawionego w poprzednim kroku, ale dla `bitonic_sort` funkcji.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Utwórz przeciążoną wersję `parallel_bitonic_sort` funkcji, która sortuje tablicę w kolejności rosnącej.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke`Algorytm zmniejsza obciążenie, wykonując ostatnią serię zadań w kontekście wywołującym. Na przykład w `parallel_bitonic_sort` funkcji pierwsze zadanie jest uruchamiane w oddzielnym kontekście, a drugie zadanie jest uruchamiane w kontekście wywołującym.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

W poniższym przykładzie wykonywane są zarówno numery seryjne, jak i równoległe algorytmu sortowania bitonicznego. W przykładzie pokazano również drukowanie do konsoli programu czas wymagany do wykonania każdego obliczenia.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
serial time: 4353
parallel time: 1248
```

[[Top](#top)]

### <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-bitonic-sort.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-bitonic-Sort. cpp**

## <a name="robust-programming"></a>Niezawodne programowanie

W tym przykładzie jest używany `parallel_invoke` algorytm zamiast klasy [concurrency:: task_group](reference/task-group-class.md) , ponieważ okres istnienia każdej grupy zadań nie wykracza poza funkcję. Zalecamy korzystanie z programu, `parallel_invoke` gdy jest to możliwe, ponieważ ma mniej nakładów wykonywania niż `task group` obiekty i dlatego umożliwia pisanie lepszego wykonywania kodu.

Równoległe wersje niektórych algorytmów działają lepiej tylko wtedy, gdy jest wystarczająca ilość pracy do wykonania. Na przykład `parallel_bitonic_merge` funkcja wywołuje wersję seryjną, `bitonic_merge` Jeśli w sekwencji występuje 500 lub mniej elementów. Możesz również zaplanować ogólną strategię sortowania na podstawie ilości pracy. Na przykład może być bardziej wydajne użycie wersji szeregowej algorytmu szybkiego sortowania, jeśli tablica zawiera mniej niż 500 elementów, jak pokazano w następującym przykładzie:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Podobnie jak w przypadku dowolnego algorytmu równoległego, zalecamy profilowanie i dostrajanie kodu zgodnie z potrzebami.

## <a name="see-also"></a>Zobacz też

[Równoległość zadań](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Funkcja parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)
