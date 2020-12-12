---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4006'
title: Ostrzeżenie kompilatora (poziom 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: 1d0b38e2ac3d224f26a0a52ac2d7f2343a1f955d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335978"
---
# <a name="compiler-warning-level-1-c4006"></a>Ostrzeżenie kompilatora (poziom 1) C4006

\#undef Oczekiwano identyfikatora

`#undef`Dyrektywa nie określiła identyfikatora do usunięcia. Dyrektywa jest ignorowana. Aby rozwiązać ten problem, należy określić identyfikator. Poniższy przykład generuje C4006:

```cpp
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```
