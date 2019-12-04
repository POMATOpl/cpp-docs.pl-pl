---
title: Błąd kompilatora C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 1d3078614ff6818dd4185b3bd5ed2f49413db16f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755957"
---
# <a name="compiler-error-c3609"></a>Błąd kompilatora C3609

"member": funkcja zapieczętowana lub Final musi być wirtualna

[Zapieczętowane](../../extensions/sealed-cpp-component-extensions.md) i [końcowe](../../cpp/final-specifier.md) słowa kluczowe są dozwolone tylko dla klasy, struktury lub funkcji członkowskiej oznaczonej `virtual`.

Poniższy przykład generuje C3609:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
