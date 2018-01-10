---
title: "C2500 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2500
dev_langs: C++
helpviewer_keywords: C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2500"></a>C2500 błąd kompilatora
"identifier1": "identifier2" jest już bezpośredniej klasie podstawowej  
  
 Klasy lub struktury występuje więcej niż raz na liście klas podstawowych.  
  
 Bezpośrednie podstawowy jest jednym wymienionych na liście podstawowej. Pośrednie podstawowy jest klasą podstawową dla jednej z klas w liście podstawowych.  
  
 Klasa nie można określić jako bezpośredniej klasie podstawowej więcej niż raz. Klasa może służyć jako pośredniej klasy podstawowej więcej niż raz.  
  
 Poniższy przykład generuje C2500:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```