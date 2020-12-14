---
description: 'Dowiedz się więcej o: błąd kompilatora C3195'
title: Błąd kompilatora C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 691aa50fcb091f240253363a23671ac4db70894f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203799"
---
# <a name="compiler-error-c3195"></a>Błąd kompilatora C3195

"operator": jest zarezerwowany i nie może być używany jako element członkowski klasy referencyjnej lub typu wartości. Operatory CLR lub WinRT muszą być zdefiniowane za pomocą słowa kluczowego "operator"

Kompilator wykrył definicję operatora przy użyciu składni Managed Extensions for C++. Należy użyć składni języka C++ dla operatorów.

Poniższy przykład generuje C3195 i pokazuje, jak to naprawić:

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```
