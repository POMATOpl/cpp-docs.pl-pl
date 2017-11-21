---
title: "C3701 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3701
dev_langs: C++
helpviewer_keywords: C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 723deeb35dc16aff4535c1961261ba705f8ee364
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3701"></a>C3701 błąd kompilatora
"Funkcja": event_source — nie ma żadnych zdarzeń  
  
 Podjęto próbę użycia [event_source —](../../windows/event-source.md) dla klasy, która nie ma żadnych metod zdarzeń. Aby naprawić ten błąd, należy dodać co najmniej jednego zdarzenia do klasy.  
  
 Poniższy przykład generuje C3701:  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```