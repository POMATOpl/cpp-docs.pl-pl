---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4239'
title: Ostrzeżenie kompilatora (poziom 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 635795392b5544f4985305a02e8534188c049224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334862"
---
# <a name="compiler-warning-level-4-c4239"></a>Ostrzeżenie kompilatora (poziom 4) C4239

użyto niestandardowego rozszerzenia: "token": konwersja z "Type" na "Type"

Ta konwersja typu nie jest dozwolona w standardzie C++, ale jest dozwolona jako rozszerzenie. To ostrzeżenie jest zawsze poprzedzone co najmniej jednym wierszem wyjaśnienia opisującym naruszanie reguły języka.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C4239.

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

Konwersja z typu całkowitego na typ wyliczeniowy nie jest ściśle dozwolona.

Poniższy przykład generuje C4239.

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```
