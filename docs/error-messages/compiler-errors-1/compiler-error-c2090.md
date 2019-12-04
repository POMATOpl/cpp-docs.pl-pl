---
title: Błąd kompilatora C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 3c87bc75e984c544646a28a663302acd5733ac25
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755944"
---
# <a name="compiler-error-c2090"></a>Błąd kompilatora C2090

Funkcja zwraca tablicę

Funkcja nie może zwracać tablicy. Zamiast tego Zwróć wskaźnik do tablicy.

Poniższy przykład generuje C2090:

```cpp
// C2090.cpp
int func1(void)[] {}   // C2090
```

Możliwe rozwiązanie:

```cpp
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```
