---
description: 'Dowiedz się więcej na temat: jak używać kombinacji do łączenia zestawów'
title: 'Porady: korzystanie z wyników połączonych w celu łączenia zestawów'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: da51bf8a2e7dd21432b9dcce73c6ead83ce23e35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172469"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Porady: korzystanie z wyników połączonych w celu łączenia zestawów

W tym temacie pokazano, jak użyć klasy [concurrency:: prekombinowanej](../../parallel/concrt/reference/combinable-class.md) do obliczenia zestawu numerów pierwszych.

## <a name="example"></a>Przykład

Poniższy przykład oblicza zestaw liczb pierwszych dwa razy. Każde obliczenie zapisuje wynik w obiekcie [std:: bitset](../../standard-library/bitset-class.md) . Przykład najpierw oblicza zestaw sekwencyjnie, a następnie oblicza równoległie zestaw. W przykładzie pokazano również drukowanie do konsoli programu czas wymagany do wykonania obu obliczeń.

W tym przykładzie zastosowano algorytm [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) i `combinable` obiekt do generowania zestawów lokalnych wątków. Następnie używa metody [concurrency:: kombinowane:: combine_each](reference/combinable-class.md#combine_each) do łączenia zestawów lokalnych wątków z zestawem końcowym.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

Następujące przykładowe dane wyjściowe dotyczą komputera, który ma cztery procesory.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `parallel-combine-primes.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Parallel-Combine-primes. cpp**

## <a name="see-also"></a>Zobacz też

[Równoległe kontenery i obiekty](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Klasa z kombinacją](../../parallel/concrt/reference/combinable-class.md)<br/>
[Metoda kombinowana:: combine_each](reference/combinable-class.md#combine_each)
