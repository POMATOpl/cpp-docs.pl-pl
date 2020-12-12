---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4457'
title: Ostrzeżenie kompilatora (poziom 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 8898189668eba95619e6bd0d0ccf1cb8ca3afdfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251417"
---
# <a name="compiler-warning-level-4-c4457"></a>Ostrzeżenie kompilatora (poziom 4) C4457

> Deklaracja elementu "*Identifier*" powoduje ukrycie parametru funkcji

Deklaracja *identyfikatora* w zakresie lokalnym ukrywa deklarację parametru funkcji o identycznej nazwie. To ostrzeżenie informuje o tym, że odwołania do *identyfikatora* w zakresie lokalnym są rozpoznawane jako wersja zadeklarowana lokalnie, a nie do parametru, który może lub nie być zamiarem. Aby rozwiązać ten problem, zalecamy nadawanie nazw zmiennych lokalnych, które nie powodują konfliktu z nazwami parametrów.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4457, ponieważ parametr `x` i zmienna lokalna `x` w `member_fn` mają takie same nazwy. Aby rozwiązać ten problem, Użyj różnych nazw dla parametrów i zmiennych lokalnych.

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
