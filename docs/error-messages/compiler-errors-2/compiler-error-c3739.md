---
title: "C3739 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3739
dev_langs: C++
helpviewer_keywords: C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3fa62f908f152e127669d1cd935fafdb75d413f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3739"></a>C3739 błąd kompilatora
"class": składnia jest obsługiwana tylko wtedy, gdy parametr "layout_dependent" od event_receiver ma wartość true  
  
 Próbowano utworzenie punktu zaczepienia cały interfejs zdarzeń, ale `layout_dependent` na [event_receiver](../../windows/event-receiver.md) atrybut nie jest prawdziwe; pojedyncze zdarzenie musi Podłącz naraz.  
  
 Poniższy przykład generuje C3739:  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```