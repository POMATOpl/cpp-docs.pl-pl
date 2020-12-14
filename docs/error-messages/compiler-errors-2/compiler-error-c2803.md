---
description: 'Dowiedz się więcej o: błąd kompilatora C2803'
title: Błąd kompilatora C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: 405c14d05bad4c505d847b8ab2648a7ace3b9a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297437"
---
# <a name="compiler-error-c2803"></a>Błąd kompilatora C2803

operator "operator" musi mieć co najmniej jeden formalny parametr typu klasy

Przeciążony operator nie ma parametru typu klasy.

Należy przekazać co najmniej jeden parametr przez odwołanie (nie używając wskaźników, ale odwołań) lub przez wartość, aby można było napisać "a < b" (a i b jest typu klasy A).

Jeśli oba parametry są wskaźnikami, będzie to czyste porównanie adresów wskaźnika i nie będzie używać konwersji zdefiniowanej przez użytkownika.

Poniższy przykład generuje C2803:

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```
