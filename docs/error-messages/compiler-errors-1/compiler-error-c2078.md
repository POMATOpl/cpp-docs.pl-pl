---
description: 'Dowiedz się więcej o: błąd kompilatora C2078'
title: Błąd kompilatora C2078
ms.date: 11/04/2016
f1_keywords:
- C2078
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
ms.openlocfilehash: 5ad78db99952c790a55dc2e1fddba0df227246d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151232"
---
# <a name="compiler-error-c2078"></a>Błąd kompilatora C2078

zbyt wiele inicjatorów

Liczba inicjatorów przekracza liczbę obiektów, które mają zostać zainicjowane.

Kompilator może wywnioskować poprawne przypisanie inicjatorów do obiektów i obiektów wewnętrznych, gdy wewnętrzne nawiasy klamrowe są opuszczony Konstruktor kopiujący z listy inicjatorów. Pełna klamra eliminuje również niejednoznaczność i skutkuje prawidłowym przypisaniem. Częściowe nawiasy klamrowe mogą spowodować C2078 z powodu niejednoznaczności w przypisaniu inicjatorów do obiektów.

Poniższy przykład generuje C2078 i pokazuje, jak to naprawić:

```cpp
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}
```
