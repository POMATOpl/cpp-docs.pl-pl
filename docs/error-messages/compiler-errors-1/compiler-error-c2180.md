---
title: "C2180 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2180
dev_langs: C++
helpviewer_keywords: C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 181309cca171c872a7c3767729a755d6e73bd288
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2180"></a>C2180 błąd kompilatora
wyrażenie kontrolne jest typu "type"  
  
 Kontrolowanie wyrażenie w `if`, `while`, `for`, lub `do` instrukcja jest rzutowany wyrażenia `void`. Aby rozwiązać ten problem, zmień wyrażenie, kontrolowanie na taki, który tworzy `bool` lub typu, który może zostać przekonwertowany na `bool`.  
  
 Poniższy przykład generuje C2180:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```