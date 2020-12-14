---
description: 'Dowiedz się więcej o: błąd kompilatora C3825'
title: Błąd kompilatora C3825
ms.date: 11/04/2016
f1_keywords:
- C3825
helpviewer_keywords:
- C3825
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
ms.openlocfilehash: c4848c32dae2ab2afb0a442b383510d59b2c2b4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249350"
---
# <a name="compiler-error-c3825"></a>Błąd kompilatora C3825

"Class": zarządzany lub WinRTclass obsługuje tylko zarządzane lub WinRTevents

Klasy zarządzane są obsługiwane tylko dla zdarzeń platformy .NET. W klasach środowisko wykonawcze systemu Windows są obsługiwane tylko zdarzenia środowisko wykonawcze systemu Windows. Aby naprawić ten błąd w kodzie zarządzanym, Zmień parametr typu `event_source` i `event_receiver` z `native` na `managed` . Alternatywnie Usuń atrybut.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3825 i pokazuje, jak to naprawić:

```cpp
// C3825a.cpp
// compile with: /clr
public delegate void del1();

[event_source(native)]           // To fix, change 'native' to 'managed' or delete this line
ref class CEventSrc
{
public:
   event del1^ event1;       // C3825

   void FireEvents() {
      event1();
   }
};

[event_receiver(native)]         // To fix, change 'native' to 'managed' or delete this line
ref class CEventRec
{
public:
   void handler1()
   {
      System::Console::WriteLine("Executing handler1().\n");
   }
   void HookEvents(CEventSrc^ pSrc)
   {
      pSrc->event1 += gcnew del1(this, &CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc^ pSrc)
   {
      pSrc->event1 -= gcnew del1(this, &CEventRec::handler1);
   }
};

int main()
{
   CEventSrc^ pEventSrc = gcnew CEventSrc;
   CEventRec^ pEventRec = gcnew CEventRec;
   pEventRec->HookEvents(pEventSrc);
   pEventSrc->FireEvents();
   pEventRec->UnhookEvents(pEventSrc);
}
```
