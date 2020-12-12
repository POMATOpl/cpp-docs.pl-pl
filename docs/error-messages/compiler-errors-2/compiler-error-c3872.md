---
description: 'Dowiedz się więcej o: błąd kompilatora C3872'
title: Błąd kompilatora C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: 860db2f94fa198246290a0e491b1a647dbc91c20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222739"
---
# <a name="compiler-error-c3872"></a>Błąd kompilatora C3872

"char": ten znak nie jest dozwolony w identyfikatorze

Kompilator języka C++ jest zgodny ze standardem C++ 11 w przypadku znaków, które są dozwolone w identyfikatorze. W identyfikatorze są dozwolone tylko niektóre zakresy znaków i uniwersalne nazwy znaków. Dodatkowe ograniczenia dotyczą początkowego znaku identyfikatora. Aby uzyskać więcej informacji i listę dozwolonych znaków i zakresów uniwersalnej nazwy znaków, zobacz [identyfikatory](../../cpp/identifiers-cpp.md).

Zakres znaków dozwolony w identyfikatorze jest mniej restrykcyjny podczas kompilowania kodu C++/CLI. Identyfikatory w kodzie skompilowane przy użyciu/CLR powinny być zgodne ze  [standardem ECMA-335: Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Poniższy przykład generuje C3872:

```cpp
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```
