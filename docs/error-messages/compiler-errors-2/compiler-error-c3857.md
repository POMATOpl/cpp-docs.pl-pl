---
title: Błąd kompilatora C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 1270d09c870bfdf9f390d6afb1625ad3e99e01a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456891"
---
# <a name="compiler-error-c3857"></a>Błąd kompilatora C3857

"type": wiele list parametrów typu nie są dozwolone.

Określono więcej niż jeden szablon lub ogólny tego samego typu, co jest niedozwolone.

Poniższy przykład spowoduje wygenerowanie C3857:

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Możliwe rozwiązanie:

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 może również wystąpić, gdy za pomocą typów ogólnych:

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Możliwe rozwiązanie:

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```