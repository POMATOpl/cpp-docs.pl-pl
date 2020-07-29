---
title: Ostrzeżenie kompilatora (poziom 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: d0179dc5f5cb9367ee83a7f40f8b9ceb368474fa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218133"
---
# <a name="compiler-warning-level-2-c4307"></a>Ostrzeżenie kompilatora (poziom 2) C4307

"operator": przepełnienie stałej całkowitej

Operator jest używany w wyrażeniu, które powoduje stałe przepełnienie przyjmowanego miejsca. Może być konieczne użycie większego typu dla stałej. **`signed int`** Zawiera mniejszą wartość niż, **`unsigned int`** ponieważ **`signed int`** używa jednego bitu do reprezentowania znaku.

Poniższy przykład generuje C4307:

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```
