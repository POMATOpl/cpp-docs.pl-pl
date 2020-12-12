---
description: 'Dowiedz się więcej o: błąd kompilatora C3609'
title: Błąd kompilatora C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 187bc6d9849c385f6adb3ae2c25e2e90e7393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223129"
---
# <a name="compiler-error-c3609"></a>Błąd kompilatora C3609

"member": funkcja zapieczętowana lub Final musi być wirtualna

[Zapieczętowane](../../extensions/sealed-cpp-component-extensions.md) i [końcowe](../../cpp/final-specifier.md) słowa kluczowe są dozwolone tylko dla klasy, struktury lub funkcji członkowskiej oznaczonej jako **`virtual`** .

Poniższy przykład generuje C3609:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
