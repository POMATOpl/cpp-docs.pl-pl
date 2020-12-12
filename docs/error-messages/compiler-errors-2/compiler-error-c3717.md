---
description: 'Dowiedz się więcej o: błąd kompilatora C3717'
title: Błąd kompilatora C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: fecd417af1eceb40ef8b8e48fda40b3ec5e5b36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189434"
---
# <a name="compiler-error-c3717"></a>Błąd kompilatora C3717

"Metoda": metoda, która wyzwala zdarzenia nie może być zdefiniowana

Zadeklarowano metodę zdarzenia, która zawiera implementację. Deklaracja metody [__event](../../cpp/event.md) nie może mieć definicji. Aby naprawić ten błąd, upewnij się, że żadne deklaracje metody zdarzeń nie mają definicji. Na przykład, w poniższym kodzie, Usuń treść funkcji z `event1` deklaracji, jak wskazano w komentarzach.

Poniższy przykład generuje C3717:

```cpp
// C3717.cpp
[event_source(native)]
class CEventSrc {
public:
   __event void event1() {   // C3717
   }

   // remove definition for event1 and substitute following declaration
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
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
