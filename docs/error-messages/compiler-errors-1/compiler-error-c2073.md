---
description: 'Dowiedz się więcej o: błąd kompilatora C2073'
title: Błąd kompilatora C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 791f07040b0a0dd70d2cb0aa8373eb6c342c5b97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209168"
---
# <a name="compiler-error-c2073"></a>Błąd kompilatora C2073

"Identyfikator": elementy częściowo zainicjowanej tablicy muszą mieć domyślny Konstruktor

Określono zbyt mało inicjatorów dla tablicy typów lub stałych zdefiniowanych przez użytkownika. Jeśli jawny inicjator i odpowiadający mu Konstruktor nie są określone dla elementu członkowskiego tablicy, należy dostarczyć konstruktora domyślnego.

Poniższy przykład generuje C2073:

```cpp
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```cpp
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```
