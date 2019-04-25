---
title: Kompilator ostrzeżenie (poziom 4) C4610
ms.date: 11/04/2016
f1_keywords:
- C4610
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
ms.openlocfilehash: ce671552083f4e6b055c52e7387d3a95e7d47c0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220583"
---
# <a name="compiler-warning-level-4-c4610"></a>Kompilator ostrzeżenie (poziom 4) C4610

obiekt "class" nigdy nie mogą zostać utworzone - wymagany Konstruktor zdefiniowany przez użytkownika

Klasa nie ma przypisanego zdefiniowanych przez użytkownika lub domyślne konstruktory. Odbywa się nie tworzenia wystąpienia. Poniższy przykład spowoduje wygenerowanie C4610:

```
// C4610.cpp
// compile with: /W4
struct A {
   int &j;

   A& A::operator=( const A& );
};   // C4610

/* use this structure definition to resolve the warning
struct B {
   int &k;

   B(int i = 0) : k(i) {
   }

   B& B::operator=( const B& );
} b;
*/

int main() {
}
```