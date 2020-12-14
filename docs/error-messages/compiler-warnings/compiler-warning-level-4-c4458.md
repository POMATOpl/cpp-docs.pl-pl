---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4458'
title: Ostrzeżenie kompilatora (poziom 4) C4458
ms.date: 11/04/2016
f1_keywords:
- C4458
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
ms.openlocfilehash: f631fe4086c69732c972161ae7bb6096232b2740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241264"
---
# <a name="compiler-warning-level-4-c4458"></a>Ostrzeżenie kompilatora (poziom 4) C4458

> Deklaracja elementu "*Identifier*" powoduje ukrycie składowej klasy

Deklaracja *identyfikatora* w zakresie lokalnym powoduje ukrycie deklaracji o identycznym *identyfikatorze* w zakresie klasy. To ostrzeżenie informuje o tym, że odwołania do *identyfikatora* w tym zakresie są rozpoznawane jako wersja zadeklarowana lokalnie, a nie do wersji elementu członkowskiego klasy, która może być lub nie być zamiarem. Aby rozwiązać ten problem, zalecamy nadawanie nazw zmiennych lokalnych, które nie powodują konfliktu z nazwami elementów członkowskich klasy.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4458, ponieważ parametr `x` i zmienna lokalna `y` w `member_fn` mają takie same nazwy jak składowe danych w klasie. Aby rozwiązać ten problem, Użyj różnych nazw dla parametrów i zmiennych lokalnych.

```cpp
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;
        // To fix this issue, change the parameter name x
        // and local name y to something that does not
        // conflict with the data member names.
    }
} s;
```
