---
title: "C3243 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3243
dev_langs: C++
helpviewer_keywords: C3243
ms.assetid: 35d8ad1a-377d-47df-be9d-c55eea23340f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0539a411d6df5d9054a6530683b2809137190c4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3243"></a>C3243 błąd kompilatora
żadna z funkcji przeciążonych nie została wprowadzona przez "interface"  
  
 Nastąpiła próba [jawnie przesłonić](../../cpp/explicit-overrides-cpp.md) elementu członkowskiego, który nie istnieje w określonym interfejsie.  
  
 Poniższy przykład generuje C3243:  
  
```  
// C3243.cpp  
#pragma warning(disable:4199)  
__interface IX14A {  
   void g();  
};  
  
__interface IX14B {  
   void f();  
   void f(int);  
};  
  
class CX14 : public IX14A, public IX14B {  
public:  
   void IX14A::g();  
   void IX14B::f();  
   void IX14B::f(int);  
};  
  
void CX14::IX14A::f()   // C3243 occurs here  
{  
}  
```