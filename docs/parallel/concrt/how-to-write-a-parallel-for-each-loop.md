---
description: 'Dowiedz się więcej na temat: jak napisać pętlę parallel_for_each'
title: 'Porady: pisanie pętli parallel_for_each'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: cb80173d3d4c78fe4d46f017d60af2c3c6659096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112235"
---
# <a name="how-to-write-a-parallel_for_each-loop"></a>Porady: pisanie pętli parallel_for_each

Ten przykład pokazuje, jak używać algorytmu [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) do obliczania liczby pierwszych liczb w obiekcie [std:: Array](../../standard-library/array-class-stl.md) równolegle.

## <a name="example"></a>Przykład

Poniższy przykład oblicza liczbę pierwszych liczb w tablicy dwa razy. W przykładzie najpierw jest używany algorytm [std:: for_each](../../standard-library/algorithm-functions.md#for_each) w celu obliczenia liczby seryjnie. W przykładzie jest używany `parallel_for_each` algorytm do wykonywania tego samego zadania równolegle. W przykładzie pokazano również drukowanie do konsoli programu czas wymagany do wykonania obu obliczeń.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-count-primes.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-Count-primes. cpp**

## <a name="robust-programming"></a>Niezawodne programowanie

Wyrażenie lambda, które przykład przekazuje do algorytmu, `parallel_for_each` używa funkcji, `InterlockedIncrement` Aby włączyć równoległe iteracje pętli, aby zwiększyć licznik jednocześnie. W przypadku korzystania z takich funkcji `InterlockedIncrement` , jak synchronizowanie dostępu do udostępnionych zasobów, można przedstawić wąskie gardła wydajności w kodzie. Można użyć mechanizmu synchronizacji bez blokady, na przykład klasy [concurrency::Binding](../../parallel/concrt/reference/combinable-class.md) , aby wyeliminować jednoczesny dostęp do udostępnionych zasobów. Aby zapoznać się z przykładem `combinable` , który używa klasy w ten sposób, zobacz [jak: używanie kombinacji w celu zwiększenia wydajności](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Zobacz też

[Algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md)<br/>
[Funkcja parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)
