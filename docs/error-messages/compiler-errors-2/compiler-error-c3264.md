---
description: 'Dowiedz się więcej o: błąd kompilatora C3264'
title: Błąd kompilatora C3264
ms.date: 11/04/2016
f1_keywords:
- C3264
helpviewer_keywords:
- C3264
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
ms.openlocfilehash: 97edaaf456a0effbd45117eeaea522cfdac0e449
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223428"
---
# <a name="compiler-error-c3264"></a>Błąd kompilatora C3264

"Class": Konstruktor klasy nie może mieć zwracanego typu

Konstruktory klas nie mogą mieć typów zwracanych.

Poniższy przykład generuje C3264:

```cpp
// C3264_2.cpp
// compile with: /clr

ref class X {
   public:
      static int X()   { // C3264
      }

      /* use the code below to resolve the error
      static X() {
      }
      */
};
int main() {
}
```
