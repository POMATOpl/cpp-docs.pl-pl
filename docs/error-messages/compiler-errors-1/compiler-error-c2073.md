---
title: Błąd kompilatora C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 2b45d512224ec32459e6da040a6abb0211278e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303323"
---
# <a name="compiler-error-c2073"></a>Błąd kompilatora C2073

'Identyfikator': elementy częściowo zainicjowanej tablicy muszą mieć domyślnego konstruktora

Zbyt mało inicjatory zostały określone w tablicy, typy zdefiniowane przez użytkownika lub stałych. Jeśli jawna inicjatora i jego odpowiedniego konstruktora, nie są określone dla elementu członkowskiego tablicy, należy podać domyślnego konstruktora.

Poniższy przykład spowoduje wygenerowanie C2073:

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```