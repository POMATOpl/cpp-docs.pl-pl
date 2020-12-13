---
description: 'Dowiedz się więcej o: błąd kompilatora C2464'
title: Błąd kompilatora C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: 2e30166529616809478927dbfe6ff1f1efb3002a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341844"
---
# <a name="compiler-error-c2464"></a>Błąd kompilatora C2464

"Identyfikator": nie można użyć "New", aby przydzielić odwołanie

Identyfikator odwołania został przydzielony do **`new`** operatora. Odwołania nie są obiektami pamięci, dlatego **`new`** nie można zwrócić do nich wskaźnika. Użyj składni deklaracji zmiennej standardowej, aby zadeklarować odwołanie.

Poniższy przykład generuje C2464:

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
