---
title: Błąd kompilatora C2326
ms.date: 11/04/2016
f1_keywords:
- C2326
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
ms.openlocfilehash: 36df63ce1ac5bcdb444721be3aa10f9867ae7c58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300900"
---
# <a name="compiler-error-c2326"></a>Błąd kompilatora C2326

'deklarator': funkcja nie ma dostępu do "name"

Kod próbuje zmodyfikować zmiennej składowej, która nie jest możliwe.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2326:

```
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