---
description: 'Dowiedz się więcej o: błąd kompilatora C3648'
title: Błąd kompilatora C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 532c65896ae5c3707c86735c661a095698417288
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203747"
---
# <a name="compiler-error-c3648"></a>Błąd kompilatora C3648

Ta składnia jawnego przesłaniania wymaga/CLR: oldSyntax

Podczas kompilowania dla najnowszej składni zarządzanej kompilator znalazł jawną składnię przesłonięcia dla poprzednich wersji, która nie jest już obsługiwana.

Aby uzyskać więcej informacji, zobacz [jawne zastąpienia](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3648:

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
