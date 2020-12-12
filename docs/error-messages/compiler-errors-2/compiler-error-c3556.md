---
description: 'Dowiedz się więcej o: błąd kompilatora C3556'
title: Błąd kompilatora C3556
ms.date: 11/04/2016
f1_keywords:
- C3556
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
ms.openlocfilehash: b608e67958757c3e31a64fcf41954b056d6af404
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262402"
---
# <a name="compiler-error-c3556"></a>Błąd kompilatora C3556

> "*Expression*": nieprawidłowy argument dla "decltype"

Kompilator nie może wywnioskować typu wyrażenia, które jest argumentem `decltype(`  `)` specyfikatora typu wyrażenia.

## <a name="example"></a>Przykład

W poniższym przykładzie kodu kompilator nie może wywnioskować typu `myFunction` argumentu, ponieważ `myFunction` jest przeciążony. Aby rozwiązać ten problem, można użyć **`static_cast`** programu do utworzenia wystąpienia wskaźnika do określonej przeciążonej funkcji w celu określenia w **`decltype`** wyrażeniu.

```cpp
// C3556.cpp
// compile with: cl /W4 /EHsc C3556.cpp
#include <iostream>

void myFunction(int);
void myFunction(float, float);

void callsMyFunction(decltype(myFunction) fn); // C3556
// One way to fix is to comment out the line above, and
// use static_cast to create specialized function pointer
// instances:
auto myFunctionInt = static_cast<void(*)(int)>(myFunction);
auto myFunctionFloatFloat = static_cast<void(*)(float,float)>(myFunction);
void callsMyFunction(decltype(myFunctionInt) fn, int n);
void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g);

void myFunction(int i) {
    std::cout << "called myFunction(" << i << ")" << std::endl;
}

void myFunction(float f, float g) {
    std::cout << "called myFunction(" << f << ", " << g << ")" << std::endl;
}

void callsMyFunction(decltype(myFunctionInt) fn, int n) {
    fn(n);
}

void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g) {
    fn(f, g);
}

int main() {
    callsMyFunction(myFunction, 42);
    callsMyFunction(myFunction, 0.1f, 2.3f);
}
```
