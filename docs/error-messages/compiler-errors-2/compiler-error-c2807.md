---
description: 'Dowiedz się więcej o: błąd kompilatora C2807'
title: Błąd kompilatora C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 8ce98ee69bf3c41e822a5ecc40dc794b443b6ff0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320626"
---
# <a name="compiler-error-c2807"></a>Błąd kompilatora C2807

drugi formalny parametr do przyrostkowego operatora "operator" musi mieć wartość "int"

Drugi parametr do operatora przyrostkowego ma nieprawidłowy typ.

Poniższy przykład generuje C2807:

```cpp
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```
