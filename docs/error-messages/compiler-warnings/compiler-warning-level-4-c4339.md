---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4339'
title: Ostrzeżenie kompilatora (poziom 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: e05a7a73ac0cbbf056e5e30db0989e7fe933d01e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294525"
---
# <a name="compiler-warning-level-4-c4339"></a>Ostrzeżenie kompilatora (poziom 4) C4339

"Type": użycie niezdefiniowanego typu wykryte w metadanych WinRT lub CLR — użycie tego typu może prowadzić do wyjątku czasu wykonywania

Nie zdefiniowano typu w kodzie, który został skompilowany dla środowisko wykonawcze systemu Windows lub środowiska uruchomieniowego języka wspólnego. Zdefiniuj typ, aby uniknąć możliwego wyjątku środowiska uruchomieniowego.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4339 i pokazuje, jak to naprawić:

```cpp
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```
