---
description: 'Dowiedz się więcej o: błąd kompilatora C2534'
title: Błąd kompilatora C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: fbdc4c292a8eb59ee9ab51de0100455139473f7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302078"
---
# <a name="compiler-error-c2534"></a>Błąd kompilatora C2534

"Identyfikator": Konstruktor nie może zwrócić wartości

Konstruktor nie może zwrócić wartości ani mieć zwracanego typu (nawet **`void`** typu zwracanego).

Ten błąd może zostać naprawiony przez usunięcie **`return`** instrukcji z definicji konstruktora.

Poniższy przykład generuje C2534:

```cpp
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
