---
title: Błąd kompilatora C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 3eb2963916cbbcbd925f755f9162ce59e9bff569
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328435"
---
# <a name="compiler-error-c3709"></a>Błąd kompilatora C3709

'Funkcja': Niewłaściwa składnia określająca zdarzenie w __hook /\__unhook

Podczas określania źródła zdarzeń za pomocą [__hook](../../cpp/hook.md) lub [__unhook](../../cpp/unhook.md), pierwszy parametr musi być metodą ważnego zdarzenia i drugi parametr musi być obiektem źródłowym ważnego zdarzenia (nie metoda).

Poniższy przykład spowoduje wygenerowanie C3709:

```
// C3709.cpp
// compile with: /LD
[event_source(native)]
class CEventSrc
{
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
   void handler1()
   {
   }

   void HookEvents(CEventSrc* pSrc)
   {
      __hook(bad, pSrc, CEventRec::handler1);   // C3709
      // Try the following line instead:
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc)
   {
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};
```