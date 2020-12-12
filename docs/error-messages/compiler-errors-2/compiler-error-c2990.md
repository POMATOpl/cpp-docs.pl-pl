---
description: 'Dowiedz się więcej o: błąd kompilatora C2990'
title: Błąd kompilatora C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 80aa15940420e9d3e452f2c3a93eefe94fd1561b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328256"
---
# <a name="compiler-error-c2990"></a>Błąd kompilatora C2990

"Class": typ inny niż Klasa jako zadeklarowany jako typ klasy

Klasa niegeneryczna lub szablonu ponownie definiuje klasę generyczną lub szablonową. Sprawdź pliki nagłówkowe pod kątem konfliktów.

Poniższy przykład generuje C2990:

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 może również wystąpić z powodu istotnej zmiany w kompilatorze języka Microsoft C++ dla programu Visual Studio 2005; kompilator wymaga teraz, aby wiele deklaracji tego samego typu były identyczne z uwzględnieniem specyfikacji szablonu.

Poniższy przykład generuje C2990:

```cpp
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```
