---
description: 'Dowiedz się więcej o: błąd kompilatora C3634'
title: Błąd kompilatora C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 21407af8a86a3f82331d0f2a1d424457d8bee833
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239249"
---
# <a name="compiler-error-c3634"></a>Błąd kompilatora C3634

"Function": nie można zdefiniować metody abstrakcyjnej zarządzanego lub WinRTclass

Metoda abstrakcyjna może być zadeklarowana w klasie Managed lub WinRT, ale nie może być zdefiniowana.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3634:

```cpp
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
