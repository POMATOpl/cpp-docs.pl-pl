---
title: C3556 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3556
dev_langs:
- C++
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9579a5d3963d516328ec4febffc212ee497c615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3556"></a>C3556 błąd kompilatora
  
> "*wyrażenie*": nieprawidłowy argument dla "decltype"  
  
Kompilator nie można wywnioskować typu wyrażenia, który jest argumentem `decltype(` *wyrażenie* `)` Specyfikator typu.  
  
## <a name="example"></a>Przykład  
  
W poniższym przykładzie kodu kompilator nie można wywnioskować typu `myFunction` argument ponieważ `myFunction` jest przeciążona. Aby rozwiązać ten problem, można użyć `static_cast` można utworzyć wystąpienia wskaźnika do danej przeciążonej funkcji, aby określić w `decltype` wyrażenia.  
  
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