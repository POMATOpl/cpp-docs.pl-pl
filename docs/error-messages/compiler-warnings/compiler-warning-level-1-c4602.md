---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4602'
title: Ostrzeżenie kompilatora (poziom 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: 7027d97c1e47fd03211a8243aa22c2aad34181c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341766"
---
# <a name="compiler-warning-level-1-c4602"></a>Ostrzeżenie kompilatora (poziom 1) C4602

\#pragma pop_macro: "Nazwa makra" nie zawiera poprzedniej #pragma push_macro dla tego identyfikatora

Jeśli używasz [pop_macro](../../preprocessor/pop-macro.md) dla określonego makra, musisz najpierw przesłać tę nazwę makra do [push_macro](../../preprocessor/push-macro.md). Na przykład poniższy przykład generuje C4602:

```cpp
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```
