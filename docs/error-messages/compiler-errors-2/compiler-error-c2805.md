---
description: 'Dowiedz się więcej o: błąd kompilatora C2805'
title: Błąd kompilatora C2805
ms.date: 11/04/2016
f1_keywords:
- C2805
helpviewer_keywords:
- C2805
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
ms.openlocfilehash: a03e9e2199482d07238c30b0c3d78a77e1221082
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320682"
---
# <a name="compiler-error-c2805"></a>Błąd kompilatora C2805

binarny operator "operator" ma za mało parametrów

Operator binarny nie ma parametrów.

Poniższy przykład generuje C2805:

```cpp
// C2805.cpp
// compile with: /c
class X {
public:
   X operator< ( void );   // C2805 must take one parameter
   X operator< ( X );   // OK
};
```
