---
description: 'Dowiedz się więcej o: błąd kompilatora C2255'
title: Błąd kompilatora C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: 9c7898ede43c9c25175854faeab5ee279a9c5635
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333851"
---
# <a name="compiler-error-c2255"></a>Błąd kompilatora C2255

"element": nie jest dozwolony poza definicją klasy

Na przykład funkcja nieczłonkowska jest zadeklarowana jako **`friend`** .

Poniższy przykład generuje C2255:

```cpp
// C2255.cpp
// compile with: /c
class A {
private:
   void func1();
   friend void func2();
};

friend void func1() {}   // C2255
void func2(){}
```
