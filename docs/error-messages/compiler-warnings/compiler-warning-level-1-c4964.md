---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4964'
title: Ostrzeżenie kompilatora (poziom 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 102c04332bd40f6f1ae95cbd025c7400fc77dbf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327926"
---
# <a name="compiler-warning-level-1-c4964"></a>Ostrzeżenie kompilatora (poziom 1) C4964

Nie określono opcji optymalizacji; Informacje o profilu nie będą zbierane

Określono [/GL](../../build/reference/gl-whole-program-optimization.md) i [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) , ale nie zażądano żadnych optymalizacji, więc nie są generowane żadne pliki. PGC, dlatego nie będzie możliwe przeprowadzenie optymalizacji z profilem.

Jeśli chcesz, aby pliki. PGC były generowane podczas uruchamiania aplikacji, Określ jedną z opcji kompilatora [/o](../../build/reference/o-options-optimize-code.md) .

Poniższy przykład generuje C4964:

```cpp
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```
