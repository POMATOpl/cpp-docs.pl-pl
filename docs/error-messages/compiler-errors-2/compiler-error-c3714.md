---
description: 'Dowiedz się więcej o: błąd kompilatora C3714'
title: Błąd kompilatora C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: a01544558a156b746c16e731584e30bab7a77825
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241628"
---
# <a name="compiler-error-c3714"></a>Błąd kompilatora C3714

"Metoda": metoda obsługi zdarzeń musi mieć taką samą konwencję wywołania jak Źródło "Metoda"

Zdefiniowano metodę procedury obsługi zdarzeń, która nie korzystała z tej samej konwencji wywoływania co źródłowa Metoda zdarzenia. Aby naprawić ten błąd, nadaj metodzie obsługi zdarzeń te same konwencje wywoływania, jak te w źródłowej metodzie zdarzenia. Na przykład, w poniższym kodzie, należy wprowadzić konwencje wywoływania `handler1` i `event1` dopasować ([__cdecl](../../cpp/cdecl.md) lub [__stdcall](../../cpp/stdcall.md) lub innych). Usunięcie słów kluczowych konwencji wywoływania z obu deklaracji spowoduje również rozwiązanie problemu i przyczynę `event1` i `handler1` domyślne [thiscall](../../cpp/thiscall.md) konwencji wywoływania. Aby uzyskać więcej informacji, zobacz [konwencje wywoływania](../../cpp/calling-conventions.md) .

Poniższy przykład generuje C3714:

```cpp
// C3714.cpp
// compile with: /c
// processor: x86
[event_source(native)]
class CEventSrc {
public:
   __event void __cdecl event1();
   // try the following line instead
   // __event void __stdcall event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void __stdcall handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714
   }
};
```
