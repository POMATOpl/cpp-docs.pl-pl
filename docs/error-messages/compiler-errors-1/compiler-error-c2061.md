---
description: 'Dowiedz się więcej o: błąd kompilatora C2061'
title: Błąd kompilatora C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: e857f4c4de90fadecdd7b7062306391b4222bcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328719"
---
# <a name="compiler-error-c2061"></a>Błąd kompilatora C2061

Błąd składniowy: Identyfikator "Identyfikator"

Kompilator znalazł identyfikator, którego nie oczekiwano. Upewnij się, że `identifier` jest zadeklarowany przed użyciem.

Inicjator może być ujęty w nawiasy. Aby uniknąć tego problemu, umieść deklarator w nawiasach lub ustaw ją **`typedef`** .

Ten błąd może być również spowodowany tym, że kompilator wykrywa wyrażenie jako argument szablonu klasy; Użyj parametru [TypeName](../../cpp/typename.md) , aby poinformować kompilator, że jest typem.

Poniższy przykład generuje C2061:

```cpp
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 może wystąpić w przypadku przekazania nazwy wystąpienia do elementu [typeid](../../extensions/typeid-cpp-component-extensions.md):

```cpp
// C2061b.cpp
// compile with: /clr
ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   System::Type ^ pType = typeid<pG>;   // C2061
   System::Type ^ pType2 = typeid<G>;   // OK
}
```
