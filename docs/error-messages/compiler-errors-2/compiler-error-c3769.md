---
description: 'Dowiedz się więcej o: błąd kompilatora C3769'
title: Błąd kompilatora C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 5ed980ed75997637a59c6f2a0f864a20297e9a97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291704"
---
# <a name="compiler-error-c3769"></a>Błąd kompilatora C3769

"Type": zagnieżdżona Klasa nie może mieć takiej samej nazwy, jak bezpośrednio otaczająca Klasa

Klasa zagnieżdżona nie może mieć takiej samej nazwy, jak bezpośrednio otaczająca Klasa.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3769.

```cpp
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```
