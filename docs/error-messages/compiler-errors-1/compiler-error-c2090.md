---
description: 'Dowiedz się więcej o: błąd kompilatora C2090'
title: Błąd kompilatora C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 224f900a20d57a35a6a6c6dcc2dc95b09c596403
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251911"
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
