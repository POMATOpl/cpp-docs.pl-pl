---
description: 'Dowiedz się więcej o: błąd kompilatora C3290'
title: Błąd kompilatora C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: 68c0e79c233f7fbd416f6bdbe42cc555c04731fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337417"
---
# <a name="compiler-error-c3290"></a>Błąd kompilatora C3290

"Type": Właściwość prosta nie może mieć typu referencyjnego

Właściwość została zadeklarowana nieprawidłowo. W przypadku deklarowania prostej właściwości kompilator tworzy zmienną, która będzie aktualizowana, i nie może mieć zmiennej odwołania śledzącego w klasie.

Aby uzyskać więcej informacji, zobacz [operator odwołania](../../extensions/tracking-reference-operator-cpp-component-extensions.md) [Właściwości](../../extensions/property-cpp-component-extensions.md) i śledzenia.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3290.

```cpp
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```
