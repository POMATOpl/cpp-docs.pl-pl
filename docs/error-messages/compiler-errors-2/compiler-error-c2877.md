---
description: 'Dowiedz się więcej o: błąd kompilatora C2877'
title: Błąd kompilatora C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: fd5a122cfed34c59e4a597bb6371a026a90c2ebb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320489"
---
# <a name="compiler-error-c2877"></a>Błąd kompilatora C2877

element "symbol" nie jest dostępny z klasy "Class"

Wszystkie składowe pochodzące z klasy podstawowej muszą być dostępne w klasie pochodnej.

Poniższy przykład generuje C2877:

```cpp
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
