---
description: 'Dowiedz się więcej o: błąd kompilatora C2477'
title: Błąd kompilatora C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 50cbb3523e6dc30dc465876435db40a80e2768fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164396"
---
# <a name="compiler-error-c2477"></a>Błąd kompilatora C2477

"member": statyczna składowa danych nie może zostać zainicjowana za pośrednictwem klasy pochodnej

Statyczny element członkowski danych klasy Template został zainicjowany nieprawidłowo. Jest to istotna zmiana w wersjach kompilatora Microsoft C++ przed programem Visual Studio .NET 2003, aby była zgodna ze standardem ISO C++.

Poniższy przykład generuje C2477:

```cpp
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```
