---
description: 'Dowiedz się więcej o: błąd kompilatora C3611'
title: Błąd kompilatora C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 9c18e8e757e3962af1f2e0fbcc0d33384f3b6329
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262298"
---
# <a name="compiler-error-c3611"></a>Błąd kompilatora C3611

"Function": funkcja zapieczętowana nie może mieć czystego specyfikatora

Funkcja zapieczętowana została zadeklarowana nieprawidłowo.  Aby uzyskać więcej informacji, zobacz [zapieczętowany](../../extensions/sealed-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3611.

```cpp
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```
