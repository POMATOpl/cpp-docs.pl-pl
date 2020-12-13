---
description: 'Dowiedz się więcej o: błąd kompilatora C2124'
title: Błąd kompilatora C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 3ccfba5dfa45cfe0b190a03b84f8b753caec681c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335208"
---
# <a name="compiler-error-c2124"></a>Błąd kompilatora C2124

dzielenie lub dzielenie modulo przez zero

Wyrażenie stałe ma zerowy mianownik. Aby rozwiązać ten problem, nie należy dzielić przez zero.

Poniższy przykład generuje C2124:

```cpp
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```
