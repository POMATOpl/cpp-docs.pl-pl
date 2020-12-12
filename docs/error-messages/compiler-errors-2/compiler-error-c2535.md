---
description: 'Dowiedz się więcej o: błąd kompilatora C2535'
title: Błąd kompilatora C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: 149ddabcde7364513379701c55d4801fd403206b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258086"
---
# <a name="compiler-error-c2535"></a>Błąd kompilatora C2535

"Identyfikator": Funkcja składowa już zdefiniowana lub zadeklarowana

Ten błąd może być spowodowany użyciem tej samej formalnej listy parametrów w więcej niż jednej definicji lub deklaracji przeciążonej funkcji.

Jeśli otrzymasz C2535 ze względu na funkcję Dispose, zobacz [destruktory i finalizatory](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) , aby uzyskać więcej informacji.

Poniższy przykład generuje C2535:

```cpp
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```
