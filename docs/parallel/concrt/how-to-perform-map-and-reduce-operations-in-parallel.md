---
description: 'Dowiedz się więcej na temat: jak wykonywać mapowanie i ograniczać operacje równolegle'
title: 'Porady: wykonywanie mapowania i zmniejszanie operacji wykonywane równolegle'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: f35c9bf4df5a79cf9568bc286ff628e2f9fd45c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209844"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Porady: wykonywanie mapowania i zmniejszanie operacji wykonywane równolegle

W tym przykładzie pokazano, jak używać algorytmów [concurrency::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) i [concurrency::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) , a klasa [concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) , aby zliczyć wystąpienia wyrazów w plikach.

Operacja *mapy* stosuje funkcję do każdej wartości w sekwencji. Operacja *redukcji* łączy elementy sekwencji w jedną wartość. Możesz użyć standardowej biblioteki języka C++ [std:: Transform](../../standard-library/algorithm-functions.md#transform) i [std:: akumulacji](../../standard-library/numeric-functions.md#accumulate) funkcji do wykonywania map i zmniejszania operacji. Jednak w celu poprawienia wydajności wielu problemów można użyć algorytmu, `parallel_transform` Aby wykonać operację mapowania równolegle i `parallel_reduce` algorytm, aby wykonać operację zmniejszania równolegle. W niektórych przypadkach można użyć `concurrent_unordered_map` do przeprowadzenia mapy i zmniejszenia w jednej operacji.

## <a name="example"></a>Przykład

Poniższy przykład zlicza wystąpienia wyrazów w plikach. Używa [std:: Vector](../../standard-library/vector-class.md) do reprezentowania zawartości dwóch plików. Operacja mapy oblicza wystąpienia każdego wyrazu w każdym wektorze. Operacja zmniejszania sumuje wyrazy w obu wektorach.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-map-reduce.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-Map-Reduce. cpp**

## <a name="robust-programming"></a>Niezawodne programowanie

W tym przykładzie można użyć `concurrent_unordered_map` klasy, która jest zdefiniowana w concurrent_unordered_map. h — do przeprowadzenia mapy i zmniejszenia w jednej operacji.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

Zazwyczaj zrównoleglanie jest tylko zewnętrzna lub wewnętrzna pętla. Zrównoleglanie wewnętrzną pętlę, jeśli masz stosunkowo mało plików, a każdy plik zawiera wiele wyrazów. Zrównoleglanie pętlę zewnętrzną, jeśli masz stosunkowo wiele plików, a każdy plik zawiera kilka wyrazów.

## <a name="see-also"></a>Zobacz też

[Algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md)<br/>
[Funkcja parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[Funkcja parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[Klasa concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
