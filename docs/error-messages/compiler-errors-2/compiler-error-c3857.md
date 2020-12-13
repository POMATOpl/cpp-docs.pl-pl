---
description: 'Dowiedz się więcej o: błąd kompilatora C3857'
title: Błąd kompilatora C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 6d4dacfc8bf18f7f2b9665058bbd418eb0615912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336134"
---
# <a name="compiler-error-c3857"></a>Błąd kompilatora C3857

"Type": listy parametrów typu wielokrotnego są niedozwolone

Określono więcej niż jeden szablon lub ogólny dla tego samego typu, co jest niedozwolone.

Poniższy przykład generuje C3857:

```cpp
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Możliwe rozwiązanie:

```cpp
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Możliwe rozwiązanie:

```cpp
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```
