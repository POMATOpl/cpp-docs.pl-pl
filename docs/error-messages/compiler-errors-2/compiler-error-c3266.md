---
description: 'Dowiedz się więcej o: błąd kompilatora C3266'
title: Błąd kompilatora C3266
ms.date: 11/04/2016
f1_keywords:
- C3266
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
ms.openlocfilehash: 8522d893b6998be92a2b6241936481a7becb0c2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283643"
---
# <a name="compiler-error-c3266"></a>Błąd kompilatora C3266

"Class": Konstruktor klasy musi mieć listę parametrów "void"

Konstruktory klas w klasie wykorzystującej Programowanie/CLR nie mogą przyjmować parametrów.

Poniższy przykład generuje C3266:

```cpp
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
