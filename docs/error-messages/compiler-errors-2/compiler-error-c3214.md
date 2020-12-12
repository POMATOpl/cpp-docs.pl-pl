---
description: 'Dowiedz się więcej o: błąd kompilatora C3214'
title: Błąd kompilatora C3214
ms.date: 11/04/2016
f1_keywords:
- C3214
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
ms.openlocfilehash: 8f1b558b37e3a9f4daa08ecdd2f90b0f7a74a2a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173821"
---
# <a name="compiler-error-c3214"></a>Błąd kompilatora C3214

"Type": nieprawidłowy typ argumentu dla parametru generycznego "param" generycznego "generic_type", nie spełnia ograniczenia "Constraint"

Typ został określony dla tworzenia wystąpienia klasy generycznej, która nie spełnia ograniczenia klasy ogólnej.

Poniższy przykład generuje C3214:

```cpp
// C3214.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A
ref class C {};

ref class X : public A {};

int main() {
   C<int>^ c = new C<int>;   // C3214
   C<X ^> ^ c2 = new C<X^>;   // OK
}
```
