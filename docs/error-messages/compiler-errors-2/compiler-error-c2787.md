---
description: 'Dowiedz się więcej o: błąd kompilatora C2787'
title: Błąd kompilatora C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 96a06908012e565bc606bf56f6a1709ee1f265a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297813"
---
# <a name="compiler-error-c2787"></a>Błąd kompilatora C2787

"Identyfikator": żaden identyfikator GUID nie został skojarzony z tym obiektem

Operator [__uuidof](../../cpp/uuidof-operator.md) przyjmuje zdefiniowany przez użytkownika typ z DOŁĄCZONYm identyfikatorem GUID lub obiektem takiego typu zdefiniowanego przez użytkownika. Ten błąd występuje, gdy argument jest typem zdefiniowanym przez użytkownika bez identyfikatora GUID.

Poniższy przykład generuje C2787:

```cpp
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```
