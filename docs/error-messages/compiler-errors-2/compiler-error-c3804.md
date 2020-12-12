---
description: 'Dowiedz się więcej o: błąd kompilatora C3804'
title: Błąd kompilatora C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: b033acefd9a583b1659755f63fdbd3781fc95ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291509"
---
# <a name="compiler-error-c3804"></a>Błąd kompilatora C3804

"property_accessor": metody dostępu dla właściwości muszą być wszystkie statyczne lub wszystkie niestatyczne

Podczas definiowania nieprostej właściwości funkcje dostępu mogą być statyczne lub wystąpienia, ale nie oba jednocześnie.

Aby uzyskać więcej informacji, zobacz [Właściwość](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3804.

```cpp
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```
