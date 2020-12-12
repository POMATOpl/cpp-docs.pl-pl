---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4553'
title: Ostrzeżenie kompilatora (poziom 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 93d775e1a91f8306240824f99da1fae107963696
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265899"
---
# <a name="compiler-warning-level-1-c4553"></a>Ostrzeżenie kompilatora (poziom 1) C4553

"operator": operator nie ma żadnego wpływu; Czy chodziło o "operator"?

Jeśli instrukcja wyrażenia ma operator bez efektów ubocznych w górnej części wyrażenia, prawdopodobnie wystąpi błąd.

Poniższy przykład generuje C4553:

```cpp
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```
