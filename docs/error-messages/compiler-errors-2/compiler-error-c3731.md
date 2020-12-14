---
description: 'Dowiedz się więcej o: błąd kompilatora C3731'
title: Błąd kompilatora C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 8a7ad836083a8c103df7becd7605a0dfd0efeea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245086"
---
# <a name="compiler-error-c3731"></a>Błąd kompilatora C3731

niezgodne zdarzenie "function1" i obsługa "function2"; Źródło zdarzeń i procedura obsługi zdarzeń muszą być tego samego typu

Źródło zdarzeń i odbiorca zdarzenia muszą mieć ten sam typ (na przykład `native` . `com` typy). Aby naprawić ten błąd, upewnij się, że typy źródła zdarzeń i programu obsługi zdarzeń pasują do siebie.

Poniższy przykład generuje C3731:

```cpp
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```
