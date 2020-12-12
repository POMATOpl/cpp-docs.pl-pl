---
description: 'Dowiedz się więcej o: błąd kompilatora C2748'
title: Błąd kompilatora C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: 64720391906777ffd5f36c53e6f7ce27940426fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123022"
---
# <a name="compiler-error-c2748"></a>Błąd kompilatora C2748

tworzenie tablicy zarządzanej lub WinRT musi mieć rozmiar tablicy lub inicjatora tablicy

Niewłaściwie sformułowano tablicę zarządzaną lub WinRT. Aby uzyskać więcej informacji, zobacz [Array](../../extensions/arrays-cpp-component-extensions.md).

Poniższy przykład generuje C2748 i pokazuje, jak to naprawić:

```cpp
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```
