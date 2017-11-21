---
title: "C3705 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3705
dev_langs: C++
helpviewer_keywords: C3705
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba08854d9d9ac6f0e644a64a80133b1d8b70a167
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3705"></a>C3705 błąd kompilatora
"Funkcja": nie można odnaleźć interfejsu zdarzeń  
  
 Należy zdefiniować interfejsu zdarzeń, aby zdarzenia COM. Należy pamiętać, że `#include` wierszy pliki nagłówkowe ATL pokazano w poniższym przykładzie są wymagane do używania zdarzeń COM. Aby naprawić ten błąd, usuń znaczniki komentarza definicji `IEvents` interfejsu w przykładowym kodzie.  
  
 Poniższy przykład generuje C3705:  
  
```  
// C3705.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following 4 lines to resolve.  
// [object, uuid("00000000-0000-0000-0000-000000000003")]  
// __interface IEvents : IUnknown {  
//    HRESULT event1([in] int i);  
// };  
  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]  
class CEventSrc : public IBase {  
public:  
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```