---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4243'
title: Ostrzeżenie kompilatora (poziom 3) C4243
ms.date: 11/04/2016
f1_keywords:
- C4243
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
ms.openlocfilehash: af82629d3f7282dd3b649f8dc35ad8bbb84174b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344188"
---
# <a name="compiler-warning-level-3-c4243"></a>Ostrzeżenie kompilatora (poziom 3) C4243

Konwersja typu "Konwersja" istnieje z "type1" na "type2", ale jest niedostępna

Wskaźnik do klasy pochodnej jest konwertowany na wskaźnik do klasy bazowej, ale Klasa pochodna dziedziczy klasę bazową z dostępem prywatnym lub chronionym.

Poniższy przykład generuje C4243:

```cpp
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```
