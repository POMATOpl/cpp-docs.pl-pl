---
description: 'Dowiedz się więcej o: błąd kompilatora C3071'
title: Błąd kompilatora C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: f99175021b87cb9c27982121567bbb0dd97b0163
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320413"
---
# <a name="compiler-error-c3071"></a>Błąd kompilatora C3071

operator "operator" może być stosowany tylko do wystąpienia klasy ref lub typu wartościowego

Nie można użyć operatora CLR w typie natywnym. Operatora można używać w klasie ref lub ref struct (typu wartości), ale nie typu natywnego, takiego jak int czy alias dla typu natywnego, takiego jak system:: Int32. Te typy nie mogą być opakowane z kodu C++ w sposób, który odwołuje się do zmiennej macierzystej, dlatego nie można użyć operatora.

Aby uzyskać więcej informacji, zobacz [śledzenie operatora odwołania](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3071.

```cpp
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```
