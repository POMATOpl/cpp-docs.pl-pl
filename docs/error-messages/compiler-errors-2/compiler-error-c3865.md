---
description: 'Dowiedz się więcej o: błąd kompilatora C3865'
title: Błąd kompilatora C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 956cbfeb5bac97cae7e9a9a411c29326062e15b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222882"
---
# <a name="compiler-error-c3865"></a>Błąd kompilatora C3865

"calling_convention": mogą być używane tylko w natywnych funkcjach składowych

Konwencja wywoływania została użyta w funkcji, która była funkcją globalną lub zarządzaną funkcją składową. Konwencji wywoływania można używać tylko w natywnej (nie zarządzanej) funkcji składowej.

Aby uzyskać więcej informacji, zobacz [konwencje wywoływania](../../cpp/calling-conventions.md).

Poniższy przykład generuje C3865:

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
