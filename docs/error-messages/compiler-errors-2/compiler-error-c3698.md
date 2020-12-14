---
description: 'Dowiedz się więcej o: błąd kompilatora C3698'
title: Błąd kompilatora C3698
ms.date: 11/04/2016
f1_keywords:
- C3698
helpviewer_keywords:
- C3698
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
ms.openlocfilehash: 5156277d8e650b71b2f2722347a0d8ed14ff24ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222973"
---
# <a name="compiler-error-c3698"></a>Błąd kompilatora C3698

"Type": nie można użyć tego typu jako argumentu "operator"

Obiekt zarządzany został niepoprawnie zadeklarowany.

Poniższy przykład generuje C3698:

```cpp
// C3698.cpp
// compile with: /clr

int main() {
   array<int>^a = new array<int>^(20);   // C3698
   array<int>^a2 = gcnew array<int>(20);   // OK
}
```
