---
description: 'Dowiedz się więcej o: błąd kompilatora C2032'
title: Błąd kompilatora C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: cb39a539dc1e360f70cc2b217d50f3a1eabcf0f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175459"
---
# <a name="compiler-error-c2032"></a>Błąd kompilatora C2032

"Identyfikator": funkcja nie może być elementem członkowskim elementu struct/Union "structorunion"

Struktura lub Unia ma funkcję członkowską, która jest dozwolona w języku C++, ale nie w C. Aby rozwiązać ten problem, skompiluj jako program w języku C++ lub Usuń funkcję członkowską.

Poniższy przykład generuje C2032:

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Możliwe rozwiązanie:

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
