---
description: 'Dowiedz się więcej o: błąd kompilatora C3628'
title: Błąd kompilatora C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: ed0c434a40e6c513580e37b5fb2fc9f44b1dc5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144407"
---
# <a name="compiler-error-c3628"></a>Błąd kompilatora C3628

"Klasa bazowa": zarządzana lub WinRTclasses obsługuje tylko publiczne dziedziczenie

Podjęto próbę użycia klasy zarządzanej lub WinRT jako [prywatnej](../../cpp/private-cpp.md) lub [chronionej](../../cpp/protected-cpp.md) klasy podstawowej. Klasa Managed lub WinRT może być używana tylko jako klasa bazowa z dostępem [publicznym](../../cpp/public-cpp.md) .

Poniższy przykład generuje C3628 i pokazuje, jak to naprawić:

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
