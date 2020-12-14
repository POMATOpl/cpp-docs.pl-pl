---
description: 'Dowiedz się więcej o: błąd kompilatora C2326'
title: Błąd kompilatora C2326
ms.date: 11/04/2016
f1_keywords:
- C2326
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
ms.openlocfilehash: 968426bfc8752ebf1c33ed37a25923a3bd48bc29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234959"
---
# <a name="compiler-error-c2326"></a>Błąd kompilatora C2326

"deklarator": funkcja nie może uzyskać dostępu do "name"

Kod próbuje zmodyfikować zmienną członkowską, co nie jest możliwe.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2326:

```cpp
// C2326.cpp
void MyFunc() {
   int i;

   class MyClass  {
   public:
      void mf() {
         i = 4;   // C2326 i is inaccessible
      }
   };
}
```
