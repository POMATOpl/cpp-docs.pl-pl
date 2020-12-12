---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4645'
title: Ostrzeżenie kompilatora (poziom 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 1002abfa66eddbf4891f9d57af96bf0b949cd483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305302"
---
# <a name="compiler-warning-level-3-c4645"></a>Ostrzeżenie kompilatora (poziom 3) C4645

Funkcja zadeklarowana z __declspec (noreturn) zawiera instrukcję return

W funkcji, która jest oznaczona modyfikatorem [noreturn](../../cpp/noreturn.md) , znaleziono instrukcję [Return](../../cpp/program-termination.md) **`__declspec`** . **`return`** Instrukcja została zignorowana.

Poniższy przykład generuje C4645:

```cpp
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```
