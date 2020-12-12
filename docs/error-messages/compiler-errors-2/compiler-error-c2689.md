---
description: 'Dowiedz się więcej o: błąd kompilatora C2689'
title: Błąd kompilatora C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: 532db26a3c0da3191c9b15215d470618e561e76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326717"
---
# <a name="compiler-error-c2689"></a>Błąd kompilatora C2689

"Function": funkcja zaprzyjaźniona nie może być zdefiniowana w ramach lokalnej klasy

Można zadeklarować, ale nie definiować funkcji zaprzyjaźnionej w klasie lokalnej.

Poniższy przykład generuje C2689:

```cpp
// C2689.cpp
// compile with: /c
void g() {
   void f2();
   class X {
      friend void f2(){}   // C2689
      friend void f2();   // OK
   };
}
```
