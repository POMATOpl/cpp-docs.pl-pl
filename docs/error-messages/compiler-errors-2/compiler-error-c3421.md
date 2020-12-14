---
description: 'Dowiedz się więcej o: błąd kompilatora C3421'
title: Błąd kompilatora C3421
ms.date: 11/04/2016
f1_keywords:
- C3421
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
ms.openlocfilehash: ccb7301eefaddda36f33cf292174c799711b3866
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316031"
---
# <a name="compiler-error-c3421"></a>Błąd kompilatora C3421

"Type": nie można wywołać finalizatora dla tej klasy, ponieważ jest on niedostępny lub nie istnieje

Finalizator jest niejawnie prywatny, dlatego nie można go wywołać spoza jego typu otaczającego.

Aby uzyskać więcej informacji, zobacz [destruktory i finalizatory w instrukcje: Definiowanie i korzystanie z klas i struktur (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3421.

```cpp
// C3421.cpp
// compile with: /clr
ref class A {};

ref class B {
   !B() {}

public:
   ~B() {}
};

int main() {
   A a;
   a.!A();   // C3421

   B b;
   b.!B();   // C3421
}
```
