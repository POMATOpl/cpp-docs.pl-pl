---
title: "C2436 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2436
dev_langs: C++
helpviewer_keywords: C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ca31514bc53a134be4b327c175b049d258e07682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2436"></a>C2436 błąd kompilatora
"identyfikator": funkcja członkowska lub zagnieżdżona klasa na liście inicjatora konstruktora  
  
 Nie można zainicjować funkcji Członkowskich lub klas lokalnych na liście inicjatora konstruktora.  
  
 Poniższy przykład generuje C2436:  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```