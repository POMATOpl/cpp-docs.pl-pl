---
description: 'Dowiedz się więcej o: błąd kompilatora C3904'
title: Błąd kompilatora C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 0b1564e609586318d23b4204242f0cb39034c4fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144186"
---
# <a name="compiler-error-c3904"></a>Błąd kompilatora C3904

"property_accessor": należy określić liczbę parametrów

Sprawdź liczbę parametrów w `get` `set` metodach i dla wymiarów właściwości.

- Liczba parametrów dla `get` metody musi być równa liczbie wymiarów właściwości lub mieć wartość zero dla nieindeksowanych właściwości.

- Liczba parametrów `set` metody musi być większa niż liczba wymiarów właściwości.

Aby uzyskać więcej informacji, zobacz [Właściwość](../../extensions/property-cpp-component-extensions.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3904.

```cpp
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

Poniższy przykład generuje C3904.

```cpp
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```
