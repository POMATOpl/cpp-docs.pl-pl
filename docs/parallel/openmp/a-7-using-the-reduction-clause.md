---
title: A.7 użycie klauzuli reduction | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e71e65bc-a25c-4f02-b507-66b52bf950a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 350e311e9e43b2ef1f16cebcac11db9123cfbe86
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426630"
---
# <a name="a7---using-the-reduction-clause"></a>A.7   Użycie klauzuli redukcji

W poniższym przykładzie pokazano klauzuli reduction ([sekcji 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) na stronie 28):

```
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```