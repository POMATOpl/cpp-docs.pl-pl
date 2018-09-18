---
title: Błąd kompilatora C3714 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7102378acc2fe12335f1f2b3579f93cf02161b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109655"
---
# <a name="compiler-error-c3714"></a>Błąd kompilatora C3714

"method": metoda obsługi zdarzeń musi mieć tą samą konwencję wywołania jako źródło "method"

Zdefiniowane metody obsługi zdarzeń, który nie użyto tą samą konwencję wywołania jako metoda źródła zdarzeń. Aby naprawić ten błąd, należy podać metodę programu obsługi zdarzeń tej samej konwencji wywoływania, jak te metody źródła zdarzeń. Na przykład w poniższym kodzie należy konwencji wywoływania `handler1` i `event1` dopasowania ([__cdecl](../../cpp/cdecl.md) lub [__stdcall](../../cpp/stdcall.md) lub inne osoby). Usunięcie wywoływanie Konwencji słowa kluczowe z obie deklaracje będą również problemu i spowodować `event1` i `handler1` na domyślne [thiscall](../../cpp/thiscall.md) konwencji wywoływania. Zobacz [Konwencje wywoływania](../../cpp/calling-conventions.md) Aby uzyskać więcej informacji.

Poniższy przykład spowoduje wygenerowanie C3714:

```
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