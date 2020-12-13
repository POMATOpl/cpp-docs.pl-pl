---
description: 'Dowiedz się więcej o: błąd kompilatora C3288'
title: Błąd kompilatora C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: 6a9de812a981909c9de3a3bb895294ea9b6968d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144823"
---
# <a name="compiler-error-c3288"></a>Błąd kompilatora C3288

"Type": niedozwolone odwołanie do typu uchwytu

Kompilator wykrył niedozwolone odwołanie do typu dojścia. Możesz odwoływać się do typu uchwytu i przypisać go do odwołania. Aby uzyskać więcej informacji, zobacz [śledzenie operatora odwołania](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3288.

```cpp
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```
