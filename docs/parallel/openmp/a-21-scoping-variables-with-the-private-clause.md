---
title: A.21   Zmienne zakresowe z klauzulą prywatną
ms.date: 11/04/2016
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
ms.openlocfilehash: 4217bcc3911ded88b9385695c8c0ac851fceae9e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616134"
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21   Zmienne zakresowe z klauzulą prywatną

Wartości `i` i `j` w poniższym przykładzie zdefiniowano przy zamykaniu z równoległego regionu:

```
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Aby uzyskać więcej informacji na temat `private` klauzuli, zobacz [sekcji 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) na stronie 25.