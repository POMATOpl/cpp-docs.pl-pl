---
description: 'Dowiedz się więcej o: błąd kompilatora C2874'
title: Błąd kompilatora C2874
ms.date: 11/04/2016
f1_keywords:
- C2874
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
ms.openlocfilehash: ac8ba9be942be7ab0179640a260d421560a6e406
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320538"
---
# <a name="compiler-error-c2874"></a>Błąd kompilatora C2874

Deklaracja using powoduje wielokrotną deklarację "symbol"

Deklaracja powoduje, że ten sam element jest definiowany dwa razy.

Poniższy przykład generuje C2874:

```cpp
// C2874.cpp
namespace Z {
   int i;
}

int main() {
   int i;
   using Z::i;   // C2874, i already declared
}
```
