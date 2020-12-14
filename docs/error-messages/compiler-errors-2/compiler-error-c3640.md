---
description: 'Dowiedz się więcej o: błąd kompilatora C3640'
title: Błąd kompilatora C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 7f26a824cc39f2b5509c6d935a95cbc5af48aca0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239184"
---
# <a name="compiler-error-c3640"></a>Błąd kompilatora C3640

"member": odwołanie lub wirtualna funkcja członkowska klasy lokalnej musi być zdefiniowana

Kompilator wymaga zdefiniowania określonych funkcji.

Poniższy przykład generuje C3640:

```cpp
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```
