---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4744'
title: Ostrzeżenie kompilatora (poziom 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: d7be7c44d0e5abb1d0e3618ffa6ed1778a6410c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228459"
---
# <a name="compiler-warning-level-1-c4744"></a>Ostrzeżenie kompilatora (poziom 1) C4744

element "var" ma inny typ w "plik1" i "plik2": "type1" i "type2"

Zmienna zewnętrzna, do której odwołuje się lub została zdefiniowana w dwóch plikach, ma różne typy w tych plikach.  Aby rozwiązać ten problem, wprowadź definicje typu tak samo lub Zmień nazwę zmiennej w jednym z plików.

C4744 jest emitowana tylko wtedy, gdy pliki są kompilowane przy użyciu/GL.  Aby uzyskać więcej informacji, zobacz [/GL (Optymalizacja całego programu)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
> C4744 zazwyczaj występuje w plikach C (nie C++), ponieważ w języku C++ Nazwa zmiennej jest uzupełniona informacjami o typie.  Gdy przykład (poniżej) jest kompilowany jako C++, zostanie wyświetlony komunikat o błędzie konsolidatora LNK2019.

## <a name="examples"></a>Przykłady

Ten przykład zawiera pierwszą definicję.

```c
// C4744.c
// compile with: /c /GL
int global;
```

Poniższy przykład generuje C4744.

```c
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```
