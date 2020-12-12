---
description: 'Dowiedz się więcej o: błąd kompilatora C2932'
title: Błąd kompilatora C2932
ms.date: 11/04/2016
f1_keywords:
- C2932
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
ms.openlocfilehash: 6ebe50056d15eb9acda90de2714437af6673c64f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320321"
---
# <a name="compiler-error-c2932"></a>Błąd kompilatora C2932

"Class": Identyfikator klasy typu został ponownie zdefiniowany jako element członkowski danych "identifier"

Nie można użyć klasy generycznej ani szablonu jako elementu członkowskiego danych.

Poniższy przykład generuje C2932:

```cpp
// C2932.cpp
// compile with: /c
template<class T>
struct TC {};

struct MyStruct {
   int TC<int>;   // C2932
   int TC;   // OK
};
```

C2932 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2932b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};

struct MyStruct {
   int GC<int>;   // C2932
   int GC;   // OK
};
```
