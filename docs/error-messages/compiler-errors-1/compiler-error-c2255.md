---
title: Błąd kompilatora C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: 758c77b5f54404321eafcc55953c44d2ac7c5412
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758830"
---
# <a name="compiler-error-c2255"></a>Błąd kompilatora C2255

"element": nie jest dozwolony poza definicją klasy

Na przykład funkcja nieczłonkowska jest zadeklarowana jako `friend`.

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
