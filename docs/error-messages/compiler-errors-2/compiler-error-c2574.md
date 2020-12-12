---
description: 'Dowiedz się więcej o: błąd kompilatora C2574'
title: Błąd kompilatora C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: 361cc52f2a76e5470109db07ccabbe6d78291a43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208895"
---
# <a name="compiler-error-c2574"></a>Błąd kompilatora C2574

"destruktor": nie może być zadeklarowany jako statyczny

Nie można zadeklarować destruktorów ani konstruktorów **`static`** .

Poniższy przykład generuje C2574:

```cpp
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```
