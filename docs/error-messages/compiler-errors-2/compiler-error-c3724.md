---
title: C3724 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3724
dev_langs:
- C++
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1715e535eeaed8b486be6052ed079eb4ee4e10c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264184"
---
# <a name="compiler-error-c3724"></a>C3724 błąd kompilatora
należy #include \<windows.h > Aby użyć wielowątkowości ze zdarzeniami  
  
 Wymagany jest plik windows.h, jeśli używasz wielowątkowości ze zdarzeniami. Aby naprawić ten błąd, Dodaj `#include <windows.h>` u góry pliku, w którym źródła zdarzeń i zdarzeń zdefiniowanych odbiorcy.  
  
```  
// C3724.cpp  
// uncomment the following line to resolve  
// #include <windows.h>  
  
[event_source(native), threading(apartment)]  
class CEventSrc {  
public:  
   __event void event1();   // C3724  
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