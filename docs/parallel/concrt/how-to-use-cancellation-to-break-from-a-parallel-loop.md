---
description: 'Dowiedz się więcej: jak używać anulowania, aby przerwać pętlę równoległą'
title: 'Porady: użyj anulowania, aby przerwać pętlę równoległą'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 0d2817e3a2645cb01d652b7858176ffce6df73c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172521"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Porady: użyj anulowania, aby przerwać pętlę równoległą

Ten przykład pokazuje, jak używać anulowania do implementowania podstawowego algorytmu wyszukiwania równoległego.

## <a name="example"></a>Przykład

Poniższy przykład używa anulowania, aby wyszukać element w tablicy. `parallel_find_any`Funkcja używa algorytmu [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) i funkcji [concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) do wyszukiwania pozycji zawierającej daną wartość. Gdy pętla równoległa znajdzie wartość, wywołuje metodę [concurrency:: cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) , aby anulować pracę w przyszłości.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

Algorytm [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) działa jednocześnie. W związku z tym nie wykonuje operacji w ustalonej kolejności. Jeśli tablica zawiera wiele wystąpień wartości, wynik może być jednym z jej pozycji.

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-array-search.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-Array-Search. cpp**

## <a name="see-also"></a>Zobacz też

[Anulowanie w PPL](cancellation-in-the-ppl.md)<br/>
[Algorytmy równoległe](../../parallel/concrt/parallel-algorithms.md)<br/>
[Funkcja parallel_for](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[Klasa cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)
