---
description: 'Dowiedz się więcej o: błąd kompilatora C2701'
title: Błąd kompilatora C2701
ms.date: 11/04/2016
f1_keywords:
- C2701
helpviewer_keywords:
- C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
ms.openlocfilehash: c82bc2f62811b8f16af4ccfaad9648efe4ee6c16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144849"
---
# <a name="compiler-error-c2701"></a>Błąd kompilatora C2701

"Function": szablon funkcji nie może być obiektem zaprzyjaźnionym klasy lokalnej

Klasa lokalna nie może mieć funkcji szablonu jako funkcji zaprzyjaźnionej.

Poniższy przykład generuje C2701:

```cpp
// C2701.cpp
// compile with: /c
template<typename T>   // OK
void f1(const T &);

void MyFunction() {
   class MyClass {
      template<typename T> friend void f2(const T &);   // C2701
   };
}
```
