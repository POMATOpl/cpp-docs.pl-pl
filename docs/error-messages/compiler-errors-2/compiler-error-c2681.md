---
description: 'Dowiedz się więcej o: błąd kompilatora C2681'
title: Błąd kompilatora C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 3b002e6260787e60377d726bcceb6db41fce532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267784"
---
# <a name="compiler-error-c2681"></a>Błąd kompilatora C2681

"Type": nieprawidłowy typ wyrażenia dla nazwy

Operator rzutowania próbował wykonać konwersję z nieprawidłowego typu. Na przykład jeśli używasz operatora [dynamic_cast](../../cpp/dynamic-cast-operator.md) , aby skonwertować wyrażenie na typ wskaźnika, wyrażenie źródłowe musi być wskaźnikiem.

Poniższy przykład generuje C2681:

```cpp
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```
