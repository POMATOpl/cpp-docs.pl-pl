---
title: "C3733 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3733
dev_langs: C++
helpviewer_keywords: C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34bf8985c609887159491ddf51617af0ed70edef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3733"></a>C3733 błąd kompilatora
"event": Niewłaściwa składnia określająca zdarzenie COM; Czy pamiętasz "__interface"?  
  
 Dla zdarzeń COM użyto nieprawidłowej składni. Aby naprawić ten błąd, należy zmienić typ zdarzenia lub popraw składnię przestrzegania zasad zdarzeń COM.  
  
 Poniższy przykład generuje C3733:  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```