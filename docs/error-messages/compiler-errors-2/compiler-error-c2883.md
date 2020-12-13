---
description: 'Dowiedz się więcej o: błąd kompilatora C2883'
title: Błąd kompilatora C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 2ff905f5f1ca8fea4f175799e576e4538bbab164
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332348"
---
# <a name="compiler-error-c2883"></a>Błąd kompilatora C2883

"name": deklaracja funkcji powoduje konflikt z elementem "identifier" wprowadzonym za pomocą deklaracji using

Podjęto próbę zdefiniowania funkcji więcej niż jeden raz. Pierwsza definicja została wykonana z przestrzeni nazw z **`using`** deklaracją. Druga była definicją lokalną.

Poniższy przykład generuje C2883:

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
