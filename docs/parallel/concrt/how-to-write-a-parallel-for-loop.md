---
title: 'Porady: pisanie pętli parallel_for'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: 8d2d54e084652a8f34b125b96c3f502dd9cdb1fa
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008966"
---
# <a name="how-to-write-a-parallel_for-loop"></a>Porady: pisanie pętli parallel_for

Ten przykład ilustruje sposób użycia [współbieżności::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) do obliczenia iloczynu dwóch macierzy.

## <a name="example-compute-the-product-of-two-matrices"></a>Przykład: Oblicz iloczyn dwóch macierzy

Poniższy przykład pokazuje `matrix_multiply` funkcję, która oblicza iloczyn dwóch macierzy kwadratowych.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example-compute-a-matrix-multiply-in-parallel"></a>Przykład: Oblicz równoległe mnożenie macierzy

Poniższy przykład pokazuje `parallel_matrix_multiply` funkcję, która używa `parallel_for` algorytmu do równoległego wykonywania pętli zewnętrznej.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

Ten przykład parallelizes pętlę zewnętrzną tylko, ponieważ wykonuje wystarczającą ilość pracy, aby korzystać z obciążania przetwarzania równoległego. Jeśli zrównoleglanie pętlę wewnętrzną, nie otrzymasz wydajności, ponieważ niewielka ilość pracy wykonywanej przez pętlę wewnętrzną nie przeniesie obciążenia do przetwarzania równoległego. W związku z tym przekształcają pętlę zewnętrzną to najlepszy sposób, aby zmaksymalizować zalety współbieżności w większości systemów.

## <a name="example-finished-parallel_for-loop-code-sample"></a>Przykład: zakończono parallel_for przykład kodu pętli

Poniższy bardziej kompletny przykład porównuje wydajność `matrix_multiply` funkcji i `parallel_matrix_multiply` funkcję.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>Kompilowanie kodu

Aby skompilować kod, skopiuj go, a następnie wklej w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-matrix-multiply.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-Matrix-Multiply. cpp**

## <a name="see-also"></a>Zobacz też

[Algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md)<br/>
[Funkcja parallel_for](reference/concurrency-namespace-functions.md#parallel_for)
