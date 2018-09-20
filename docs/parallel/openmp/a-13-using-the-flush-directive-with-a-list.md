---
title: A.13 użycie dyrektywy flush z listą | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6c9d0736-07c2-47b1-a216-5293f03b6397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 757173c98caf156567e1924434f5ad73b3e48885
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379160"
---
# <a name="a13---using-the-flush-directive-with-a-list"></a>A.13   Użycie dyrektywy opróżniania z listą

W poniższym przykładzie użyto `flush` dyrektywę dla typu punkt-punkt synchronizacji określonych obiektów między parami wątków:

```
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```