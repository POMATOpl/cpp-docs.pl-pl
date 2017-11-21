---
title: "Kompilatora (poziom 1) ostrzeżenie C4553 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4553
dev_langs: C++
helpviewer_keywords: C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a15efc1ab043d7927bf45c886c6dcef61551b76f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4553"></a>Kompilator C4553 ostrzegawcze (poziom 1)
"operator": operator nie ma żadnego wpływu; Czy planowane "operator"?  
  
 Jeśli Instrukcja wyrażenia operator o nie działa po stronie jak wartość górnej części wyrażenia, prawdopodobnie jest błąd.  
  
 Poniższy przykład generuje C4553:  
  
```  
// C4553.cpp  
// compile with: /W1  
int func()  
{  
   return 0;  
}  
  
int main()  
{  
   int i;  
   i == func();   // C4553  
   // try the following line instead  
   // i = func();  
}  
```