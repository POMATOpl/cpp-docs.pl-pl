---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4461'
title: Ostrzeżenie kompilatora (poziom 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 2efb92ca26f9e6cf76f7777c8a50ac657f73554d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311009"
---
# <a name="compiler-warning-level-1-c4461"></a>Ostrzeżenie kompilatora (poziom 1) C4461

"Type": Ta klasa ma finalizator "Finalizer", ale nie ma destruktora "dtor"

Obecność finalizatora w typie oznacza zasoby do usunięcia. Chyba że finalizator jest jawnie wywoływany z destruktora typu, środowisko uruchomieniowe języka wspólnego określa, kiedy ma być uruchamiany finalizator, gdy obiekt wykracza poza zakres.

Jeśli zdefiniujesz destruktor w typie i jawnie wywoła finalizator z destruktora, można w sposób jednoznaczny uruchomić finalizator.

Aby uzyskać więcej informacji, zobacz [destruktory i finalizatory](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4461.

```cpp
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```
