---
title: Błąd kompilatora C3825 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3825
dev_langs:
- C++
helpviewer_keywords:
- C3825
ms.assetid: 18e204a1-f26e-42c6-8d74-2b49cc95f940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdc3b612ea1ce7bdcf83c72350b4d13a6790d11f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049725"
---
# <a name="compiler-error-c3825"></a>Błąd kompilatora C3825

"class": zarządzane lub WinRTclass można tylko zarządzane pomocy technicznej lub WinRTevents

W zarządzanych klas obsługiwane są tylko zdarzenia platformy .NET. Tylko zdarzenia środowiska uruchomieniowego Windows są obsługiwane w klasy środowiska wykonawczego Windows. Aby naprawić ten błąd w kodzie zarządzanym, Zmień parametr typu `event_source` i `event_receiver` z `native` do `managed`. Możesz też usunąć ten atrybut.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3825 i pokazuje, jak go naprawić:

```
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