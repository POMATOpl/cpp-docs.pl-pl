---
title: "C3556 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3556
dev_langs:
- C++
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4cff9466ff006f303913f52101db57708020ed8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
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