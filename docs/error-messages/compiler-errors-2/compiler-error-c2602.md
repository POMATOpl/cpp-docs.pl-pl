---
title: "C2602 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2602
dev_langs: C++
helpviewer_keywords: C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6b34901c2585d06f5ca5c50e16455879bfa3a0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2602"></a>C2602 błąd kompilatora
"class::Identifier" nie jest elementem członkowskim klasy podstawowej "class"  
  
 `Identifier`nie są dostępne, ponieważ nie jest elementem członkowskim dziedziczone z dowolnej klasy podstawowej.  
  
 Poniższy przykład generuje C2602:  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```