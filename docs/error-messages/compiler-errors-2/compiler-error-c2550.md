---
title: "C2550 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2550
dev_langs: C++
helpviewer_keywords: C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bc95d61f1e9a0242e206d1e2193715a64a5549b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2550"></a>C2550 błąd kompilatora
'Identyfikator': listy inicjatorów konstruktora są dozwolone tylko dla definicji konstruktora  
  
 W definicji funkcji, która nie jest konstruktorem jest używana lista inicjatora klasy podstawowej.  
  
 Poniższy przykład generuje C2550:  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```