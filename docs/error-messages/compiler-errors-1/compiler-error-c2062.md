---
description: 'Dowiedz się więcej o: błąd kompilatora C2062'
title: Błąd kompilatora C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: ef477fba9bb1208076dd6969cb78b7495d5536e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328647"
---
# <a name="compiler-error-c2062"></a>Błąd kompilatora C2062

nieoczekiwany typ "Type"

Kompilator nie oczekiwał nazwy typu.

Poniższy przykład generuje C2062:

```cpp
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 może również wystąpić ze względu na sposób, w jaki kompilator obsługuje niezdefiniowane typy na liście parametrów konstruktora. Jeśli kompilator napotyka niezdefiniowany typ (błędny), zakłada, że Konstruktor jest wyrażeniem i problemy C2062. Aby rozwiązać ten problem, należy użyć zdefiniowanych typów na liście parametrów konstruktora.
