---
description: 'Dowiedz się więcej o: błąd kompilatora C2021'
title: Błąd kompilatora C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 823d9c3d42f1df7bc6f6f398dafd804daef76110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175641"
---
# <a name="compiler-error-c2021"></a>Błąd kompilatora C2021

oczekiwana wartość wykładnika, a nie "Character"

Znak używany jako wykładnik stałej zmiennoprzecinkowej nie jest prawidłową liczbą. Upewnij się, że używasz wykładnika, która znajduje się w zakresie.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2021:

```cpp
// C2021.cpp
float test1=1.175494351E;   // C2021
```

Możliwe rozwiązanie:

```cpp
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```
