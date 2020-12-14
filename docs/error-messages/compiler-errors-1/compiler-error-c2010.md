---
description: 'Dowiedz się więcej o: błąd kompilatora C2010'
title: Błąd kompilatora C2010
ms.date: 11/04/2016
f1_keywords:
- C2010
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
ms.openlocfilehash: 8a96c30103d46c23f3b678a2fa84abf34445dd11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221036"
---
# <a name="compiler-error-c2010"></a>Błąd kompilatora C2010

"Character": nieoczekiwany w formalnej liście parametrów makra

Znak jest nieprawidłowo używany na liście parametrów formalnych definicji makra. Usuń znak, aby rozwiązać ten problem.

Poniższy przykład generuje C2010:

```cpp
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```
