---
description: 'Dowiedz się więcej o: błąd kompilatora C2272'
title: Błąd kompilatora C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 5a46c68a09eaec9fc33ef4eaa64afaebea411659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336250"
---
# <a name="compiler-error-c2272"></a>Błąd kompilatora C2272

"Function": Modyfikatory niedozwolone dla statycznych funkcji składowych

**`static`** Funkcja członkowska jest zadeklarowana przy użyciu specyfikatora modelu pamięci, takiego jak [const](../../cpp/const-cpp.md) lub [volatile](../../cpp/volatile-cpp.md), a takie Modyfikatory nie są dozwolone w **`static`** funkcjach składowych.

Poniższy przykład generuje C2272:

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
