---
title: "C2073 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2073
dev_langs: C++
helpviewer_keywords: C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 28f44a0a51e5b1ff1c6cb39e8a330c4ac0bd3154
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2073"></a>C2073 błąd kompilatora
'Identyfikator': elementy częściowo zainicjowanej tablicy muszą mieć domyślnego konstruktora  
  
 Za mało inicjatory zostały określone dla tablicy typy danych zdefiniowane przez użytkownika lub stałymi. Jeśli nie podano inicjatora jawne i jego odpowiedniego konstruktora dla elementu członkowskiego tablicy, należy podać konstruktora domyślnego.  
  
 Poniższy przykład generuje C2073:  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```