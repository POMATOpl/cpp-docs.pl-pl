---
title: "C2877 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2877
dev_langs: C++
helpviewer_keywords: C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 24bfc3cbf531e31add96d333e6da723dba4444a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2877"></a>C2877 błąd kompilatora
"symbol" nie jest dostępny z "class"  
  
 Wszystkie elementy członkowskie pochodzi od klasy podstawowej muszą być dostępne w klasie pochodnej.  
  
 Poniższy przykład generuje C2877:  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```