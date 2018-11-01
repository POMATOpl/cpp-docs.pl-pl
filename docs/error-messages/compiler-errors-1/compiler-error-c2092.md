---
title: Błąd kompilatora C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: d3d0b0e62fbc5f8ad90b3fee5fe39c6bdaba7c2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644616"
---
# <a name="compiler-error-c2092"></a>Błąd kompilatora C2092

Typ elementu tablicy "tablicy name" nie może być funkcją

Tablice funkcje nie są dozwolone. Skorzystaj z tablicy wskaźników do funkcji.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2092:

```
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

## <a name="example"></a>Przykład

Możliwe rozwiązanie:

```
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```