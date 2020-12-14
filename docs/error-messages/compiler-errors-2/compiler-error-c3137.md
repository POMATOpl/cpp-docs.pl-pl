---
description: 'Dowiedz się więcej o: błąd kompilatora C3137'
title: Błąd kompilatora C3137
ms.date: 11/04/2016
f1_keywords:
- C3137
helpviewer_keywords:
- C3137
ms.assetid: 70bb1313-2e87-43ed-a0d8-33fa6ff475e4
ms.openlocfilehash: 7c4954e66eb019eaa11e8e17b760926e5396c0ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239327"
---
# <a name="compiler-error-c3137"></a>Błąd kompilatora C3137

"Property": nie można zainicjować właściwości

Nie można zainicjować właściwości, na przykład na liście inicjalizacji konstruktora.

Poniższy przykład generuje C3137:

```cpp
// C3137.cpp
// compile with: /clr /c
ref class CMyClass {
public:
   property int Size {
      int get() {
         return 0;
      }
      void set( int i ) {}
   }

   CMyClass() : Size( 1 ) {   // C3137
      // to resolve this C3137, remove the initializer from the
      // ctor declaration and perform the assignment as follows
      // Size = 1;
   }
};
```
