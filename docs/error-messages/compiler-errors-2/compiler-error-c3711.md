---
description: 'Dowiedz się więcej o: błąd kompilatora C3711'
title: Błąd kompilatora C3711
ms.date: 11/04/2016
f1_keywords:
- C3711
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
ms.openlocfilehash: 5ced0d5e83c149f3634053680aa52821e0d9bbe8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241693"
---
# <a name="compiler-error-c3711"></a>Błąd kompilatora C3711

"Metoda": Metoda niezarządzanego źródła zdarzeń musi zwracać typ void lub całkowity

Zdefiniowano metodę w źródle zdarzeń, która nie zwróciła typu void lub całkowitego. Aby naprawić ten błąd, upewnij się, że program obsługi zdarzeń i zdarzeń ma zwracany typ **`void`** lub typ całkowity, taki jak **`int`** lub **`long`** .

Poniższy przykład generuje C3711:

```cpp
// C3711.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[event_source(native)]
class CEventSrc {
public:
   __event float event1();   // C3711
   // try the following line instead
   // __event int event1();
   // also change the handler, below
};

[event_receiver(native)]
class CEventRec {
public:
   float handler1() {         // change float to int
      return 0.0;             // change 0.0 to 0
   }
   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
