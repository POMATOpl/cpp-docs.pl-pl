---
description: 'Dowiedz się więcej o: błąd kompilatora C2589'
title: Błąd kompilatora C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: b874988f65ef41a9cde19e4c0229a6cb54859b28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177500"
---
# <a name="compiler-error-c2589"></a>Błąd kompilatora C2589

"Identyfikator": niedozwolony token po prawej stronie "::"

Jeśli klasa, struktura lub nazwa Unii pojawia się po lewej stronie operatora rozpoznawania zakresu (podwójne dwukropek), token po prawej stronie musi być klasą, strukturą lub składową Unii. W przeciwnym razie każdy identyfikator globalny może pojawić się po prawej stronie.

Nie można obciążać operatora rozpoznawania zakresu.

Poniższy przykład generuje C2589:

```cpp
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```
