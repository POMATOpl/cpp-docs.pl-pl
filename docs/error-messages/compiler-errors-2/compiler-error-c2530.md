---
description: 'Dowiedz się więcej o: błąd kompilatora C2530'
title: Błąd kompilatora C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 07980fb6d87b4e84bc0b253ccd317eba02fa81af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258112"
---
# <a name="compiler-error-c2530"></a>Błąd kompilatora C2530

"Identyfikator": odwołania muszą być zainicjowane

Należy zainicjować odwołanie, jeśli zostało zadeklarowane, chyba że zostało już zadeklarowane:

- Za pomocą słowa kluczowego [extern](../../cpp/extern-cpp.md).

- Jako element członkowski klasy, struktury lub Unii (i jest inicjowany w konstruktorze).

- Jako parametr w deklaracji lub definicji funkcji.

- Jako zwracany typ funkcji.

Poniższy przykład generuje C2530:

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
