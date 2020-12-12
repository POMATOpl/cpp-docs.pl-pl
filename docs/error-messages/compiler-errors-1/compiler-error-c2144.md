---
description: 'Dowiedz się więcej o: błąd kompilatora C2144'
title: Błąd kompilatora C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: 172ccb897937008aa305616eea19f234dfc6a3bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235505"
---
# <a name="compiler-error-c2144"></a>Błąd kompilatora C2144

> Błąd składniowy: element "*Type*" powinien być poprzedzony "*tokenem*"

Kompilator oczekiwał *tokenu* i znaleziono *Typ* .

Ten błąd może być spowodowany brakiem zamykającego nawiasu klamrowego, prawego nawiasu lub średnika.

C2144 może również wystąpić podczas próby utworzenia makra ze słowa kluczowego CLR, które zawiera biały znak.

Jeśli próbujesz wykonać przekazywanie dalej, możesz również zobaczyć C2144. Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2144 i przedstawia sposób jego rozwiązania:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Poniższy przykład generuje C2144 i przedstawia sposób jego rozwiązania:

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```
