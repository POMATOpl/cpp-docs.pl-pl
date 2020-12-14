---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4456'
title: Ostrzeżenie kompilatora (poziom 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: f066de07b0c6bf7a7b5de3143909e402b0fedde3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241316"
---
# <a name="compiler-warning-level-4-c4456"></a>Ostrzeżenie kompilatora (poziom 4) C4456

> Deklaracja elementu "*Identifier*" powoduje ukrycie poprzedniej deklaracji lokalnej

Deklaracja *identyfikatora* w zakresie lokalnym powoduje ukrycie deklaracji poprzedniej lokalnej deklaracji o tej samej nazwie. To ostrzeżenie informuje o tym, że odwołania do *identyfikatora* w zakresie lokalnym są rozpoznawane jako wersja zadeklarowana lokalnie, a nie w poprzedniej lokalizacji lokalnej, która może być lub nie być zamiarem. Aby rozwiązać ten problem, zalecamy nadawanie nazw zmiennych lokalnych, które nie powodują konfliktu z innymi nazwami lokalnymi.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4456, ponieważ Zmienna sterująca pętli `int x` i zmienna lokalna `double x` w `member_fn` mają takie same nazwy. Aby rozwiązać ten problem, Użyj różnych nazw zmiennych lokalnych.

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
