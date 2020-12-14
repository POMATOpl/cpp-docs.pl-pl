---
description: 'Dowiedz się więcej o: błąd kompilatora C3282'
title: Błąd kompilatora C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 9455f7e109da0efa87b215f0695eeeb41648c2b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311893"
---
# <a name="compiler-error-c3282"></a>Błąd kompilatora C3282

listy parametrów ogólnych mogą występować tylko w zarządzanych lub WinRTclasses, strukturach lub funkcjach

Lista parametrów ogólnych została nieprawidłowo użyta.  Aby uzyskać więcej informacji, zobacz [Ogólne](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3282 i pokazuje, jak rozwiązać ten problem.

```cpp
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```
