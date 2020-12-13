---
description: 'Dowiedz się więcej o: błąd kompilatora C3299'
title: Błąd kompilatora C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: ab86a675eb13b975943130802ae98679dbc1cbb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337403"
---
# <a name="compiler-error-c3299"></a>Błąd kompilatora C3299

"member_function": nie można określić ograniczeń, są one dziedziczone z metody podstawowej

Podczas zastępowania ogólnej funkcji składowej nie można określać klauzul ograniczenia (powtarzające się ograniczenia wynikają z tego, że ograniczenia nie są dziedziczone).

Klauzule ograniczenia dotyczące funkcji ogólnej, która jest zastępowana, zostaną Odziedziczone.

Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3299.

```cpp
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```
