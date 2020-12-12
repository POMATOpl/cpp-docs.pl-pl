---
description: 'Dowiedz się więcej o: błąd kompilatora C3072'
title: Błąd kompilatora C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 02876a6983a47ce76f6e089bafde68af41034131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320282"
---
# <a name="compiler-error-c3072"></a>Błąd kompilatora C3072

> nie można zastosować operatora "*operator-Name*" do wystąpienia klasy ref

Użyj operatora jednoargumentowego *operatora nazwy* , aby skonwertować wystąpienie klasy ref do typu dojścia

Typ CLR wymaga operatorów CLR, nienatywnych (lub standardowych).  Aby uzyskać więcej informacji, zobacz [śledzenie operatora odwołania](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3072.

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```
