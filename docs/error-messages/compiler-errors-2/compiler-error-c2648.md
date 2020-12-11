---
description: 'Dowiedz się więcej o: błąd kompilatora C2648'
title: Błąd kompilatora C2648
ms.date: 11/04/2016
f1_keywords:
- C2648
helpviewer_keywords:
- C2648
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
ms.openlocfilehash: e8e417fa54e0c198cb6adba78932232c6c33b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160769"
---
# <a name="compiler-error-c2648"></a>Błąd kompilatora C2648

"Identyfikator": użycie składowej jako parametru domyślnego wymaga statycznej składowej

Niestatyczny element członkowski jest używany jako parametr domyślny.

Poniższy przykład generuje C2648:

```cpp
// C2648.cpp
// compile with: /c
class C {
public:
   int i;
   static int j;
   void func1( int i = i );  // C2648  i is not static
   void func2( int i = j );  // OK
};
```
