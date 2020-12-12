---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4610'
title: Ostrzeżenie kompilatora (poziom 4) C4610
ms.date: 11/04/2016
f1_keywords:
- C4610
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
ms.openlocfilehash: 6a655cbafc330738747120b3e768e06eefd6fcc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168309"
---
# <a name="compiler-warning-level-4-c4610"></a>Ostrzeżenie kompilatora (poziom 4) C4610

nie można utworzyć wystąpienia obiektu "Class" — wymagany Konstruktor zdefiniowany przez użytkownika

Klasa nie ma konstruktorów zdefiniowanych przez użytkownika lub domyślnego. Nie jest wykonywane Tworzenie wystąpienia. Poniższy przykład generuje C4610:

```cpp
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
