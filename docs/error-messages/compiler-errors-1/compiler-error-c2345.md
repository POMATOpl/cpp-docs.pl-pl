---
description: 'Dowiedz się więcej o: błąd kompilatora C2345'
title: Błąd kompilatora C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: 021c792a93fa27712087908ab30e1ddec84d08fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298412"
---
# <a name="compiler-error-c2345"></a>Błąd kompilatora C2345

align (Value): niedozwolona wartość wyrównania

Przeszedł wartość do [wyrównania](../../cpp/align-cpp.md) słowo kluczowe, które jest poza dozwolonym zakresem.

Poniższy kod generuje C2345

```cpp
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```
