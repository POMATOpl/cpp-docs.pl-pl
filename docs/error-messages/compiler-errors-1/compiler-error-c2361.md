---
title: "C2361 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2361
dev_langs: C++
helpviewer_keywords: C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: afbc770118f42794639cbce92f8d360446b0ae9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2361"></a>C2361 błąd kompilatora
Inicjalizacja "identyfikatora" jest pomijana przy etykiecie "default"  
  
 Inicjowanie `identifier` był pomijany w `switch` instrukcji. Nie można przeskoczyć poza deklaracji z inicjatora, chyba że deklaracja jest ujęta w bloku. (Chyba że jest on zadeklarowany w bloku, zmienna znajduje się w zakresie do końca `switch` instrukcji.)  
  
 Poniższy przykład generuje C2361:  
  
```  
// C2361.cpp  
void func( void ) {  
   int x;  
   switch (x) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   default :   // C2361 error  
      int k = 1;  
   }  
}  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C2361b.cpp  
// compile with: /c  
void func( void ) {  
   int x = 0;  
   switch (x) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   default :  
      int k = 1;  
   }  
}  
```