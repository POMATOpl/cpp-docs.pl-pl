---
title: "Kompilatora (poziom 1) ostrzeżenie C4630 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4630
dev_langs: C++
helpviewer_keywords: C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93d6bd976876f8abea6a0caf33fcd47860b19682
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4630"></a>Kompilator C4630 ostrzegawcze (poziom 1)
"symbol": Specyfikator klasy magazynu "extern" niedozwolony w definicji elementu członkowskiego  
  
 Element członkowski danych lub funkcja członkowska jest zdefiniowany jako `extern`. Elementy członkowskie nie może być zewnętrzny, mimo że można całych obiektów. Kompilator ignoruje `extern` — słowo kluczowe. Poniższy przykład generuje C4630:  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```