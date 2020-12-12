---
description: 'Dowiedz się więcej na temat: jak używać kombinacji w celu poprawy wydajności'
title: 'Porady: korzystanie z wyników połączonych do poprawiania wydajności'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: b9ab906f00f32fee59e2dd9a1131fe87fcbc53a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283306"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Porady: korzystanie z wyników połączonych do poprawiania wydajności

Ten przykład pokazuje, jak używać klasy [concurrency:: prekombinowanej](../../parallel/concrt/reference/combinable-class.md) do obliczania sumy liczb w obiekcie [std:: Array](../../standard-library/array-class-stl.md) , który jest podstawowy. `combinable`Klasa podnosi wydajność, eliminując stan udostępniony.

> [!TIP]
> W niektórych przypadkach mapowanie równoległe ([współbieżność::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) i zmniejszenie ([concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) może zapewnić lepszą wydajność `combinable` . Aby uzyskać przykład, który używa operacji map i zmniejsz, aby uzyskać te same wyniki co ten przykład, zobacz [algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md).

## <a name="example---accumulate"></a>Przykład — gromadzenie

W poniższym przykładzie zastosowano funkcję [std:: akumulacj](../../standard-library/numeric-functions.md#accumulate) , aby obliczyć sumę elementów w tablicy, która jest podstawowa. W tym przykładzie `a` jest `array` obiektem, a `is_prime` funkcja określa, czy jego wartość wejściowa jest podstawowa.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example---parallel_for_each"></a>Przykład — parallel_for_each

W poniższym przykładzie pokazano algorytmie sposób zrównoleglanie poprzedniego przykładu. W tym przykładzie zastosowano algorytm [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) , aby przetworzyć tablicę równolegle, a obiekt [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) do synchronizowania dostępu do `prime_sum` zmiennej. Ten przykład nie jest skalowany, ponieważ każdy wątek musi oczekiwać na udostępnienie zasobu udostępnionego.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example---combinable"></a>Przykład — do kombinacji

Poniższy przykład używa obiektu, `combinable` Aby zwiększyć wydajność poprzedniego przykładu. Ten przykład eliminuje konieczność stosowania obiektów synchronizacji; skaluje się, ponieważ `combinable` obiekt pozwala na wykonywanie zadania niezależnie od każdego wątku.

`combinable`Obiekt jest zazwyczaj używany w dwóch krokach. Najpierw należy utworzyć serię szczegółowych obliczeń przez równoległe wykonywanie pracy. Następnie połącz (lub Zmniejsz) obliczenia w końcowym wyniku. W tym przykładzie zastosowano metodę [concurrency:: kombinowane:: local](reference/combinable-class.md#local) , aby uzyskać odwołanie do sumy lokalnej. Następnie używa metody [concurrency:: kombinowane:: łączenie](reference/combinable-class.md#combine) i obiektu [lu std::p](../../standard-library/plus-struct.md) do łączenia lokalnych obliczeń w wyniku końcowym.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example---serial-and-parallel"></a>Przykład — serial i Parallel

Poniższy kompletny przykład oblicza sumę liczb pierwszych jednocześnie i jednocześnie. Przykład drukuje do konsoli czas wymagany do wykonania obu obliczeń.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-sum-of-primes.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-sum-of-primes. cpp**

## <a name="robust-programming"></a>Niezawodne programowanie

Aby uzyskać przykład, który używa operacji map i zmniejsz, aby utworzyć te same wyniki, zobacz [algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>Zobacz też

[Równoległe kontenery i obiekty](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Klasa z kombinacją](../../parallel/concrt/reference/combinable-class.md)<br/>
[Klasa critical_section](../../parallel/concrt/reference/critical-section-class.md)
