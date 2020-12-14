---
description: 'Dowiedz się więcej o: błąd kompilatora C2767'
title: Błąd kompilatora C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 4acd75d1b7782a7eb694e7b91fc19cac45a6319e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239483"
---
# <a name="compiler-error-c2767"></a>Błąd kompilatora C2767

niezgodność wymiaru zarządzanego lub WinRTarray: oczekiwano N argumentów-podano M

Deklaracja tablicy Managed lub WinRT została nieprawidłowo sformułowana. Aby uzyskać więcej informacji, zobacz [Array](../../extensions/arrays-cpp-component-extensions.md).

Poniższy przykład generuje C2767 i pokazuje, jak to naprawić:

```cpp
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```
