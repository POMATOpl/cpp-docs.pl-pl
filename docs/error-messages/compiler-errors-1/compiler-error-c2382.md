---
description: 'Dowiedz się więcej o: błąd kompilatora C2382'
title: Błąd kompilatora C2382
ms.date: 11/04/2016
f1_keywords:
- C2382
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
ms.openlocfilehash: 31996423a059f3ec337d6ab8992360bb50508602
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185950"
---
# <a name="compiler-error-c2382"></a>Błąd kompilatora C2382

"Function": zmiana definicji; Różne specyfikacje wyjątków

W obszarze [/za](../../build/reference/za-ze-disable-language-extensions.md)ten błąd wskazuje, że próbowano przeciążać funkcję tylko w [specyfikacji wyjątku](../../cpp/exception-specifications-throw-cpp.md).

Poniższy przykład generuje C2382:

```cpp
// C2382.cpp
// compile with: /Za /c
void f1(void) throw(int) {}
void f1(void) throw(char) {}   // C2382
void f2(void) throw(char) {}   // OK
```
