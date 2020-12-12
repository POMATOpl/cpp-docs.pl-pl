---
description: 'Dowiedz się więcej o: błąd kompilatora C2425'
title: Błąd kompilatora C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: 03e3ca02e0ceff70135ce14ee982d2d5a0009982
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190227"
---
# <a name="compiler-error-c2425"></a>Błąd kompilatora C2425

"token": niestałe wyrażenie w "context"

Token stanowi część wyrażenia niestałego w tym kontekście.

Aby rozwiązać ten problem, Zastąp token słowem stałym lub wyliczeniem.

Poniższy przykład generuje C2425:

```cpp
// C2425.cpp
// processor: x86
int main() {
   int i = 3;
   __asm {
      mov eax, [ebp - i]   // C2425
      mov eax, [ebp - 3]   // OK
   }
}
```
