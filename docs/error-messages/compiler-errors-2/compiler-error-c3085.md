---
description: 'Dowiedz się więcej o: błąd kompilatora C3085'
title: Błąd kompilatora C3085
ms.date: 11/04/2016
f1_keywords:
- C3085
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
ms.openlocfilehash: e4525a0862f4d32a7fd5ca924934b6679b2a7a6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116395"
---
# <a name="compiler-error-c3085"></a>Błąd kompilatora C3085

"Konstruktor": Konstruktor nie może być "słowo kluczowe"

Konstruktor został zadeklarowany nieprawidłowo. Aby uzyskać więcej informacji, zobacz [specyfikatory przesłonięć](../../extensions/override-specifiers-cpp-component-extensions.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3085.

```cpp
// C3085.cpp
// compile with: /c /clr
ref struct S {
   S() abstract;   // C3085
   S(S%) abstract;   // C3085
};

ref struct T {
   T() sealed {}   // C3085
   T(T%) sealed {}   // C3085
};
```
