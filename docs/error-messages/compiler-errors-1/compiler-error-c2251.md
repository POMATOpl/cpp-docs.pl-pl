---
title: C2251 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2251
dev_langs:
- C++
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5017494e5b16363a970d2ac0bef8bcf1c088b413
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169858"
---
# <a name="compiler-error-c2251"></a>C2251 błąd kompilatora
przestrzeń nazw "namespace" nie ma element członkowski "członek" - Czy chodziło o "członek"?  
  
 Kompilator nie mógł znaleźć identyfikatora w określonej przestrzeni nazw.  
  
 Poniższy przykład generuje C2251:  
  
```  
// C2251.cpp  
// compile with: /c  
namespace A {  
   namespace B {  
      void f1();  
   }  
  
   using namespace B;  
}  
  
void A::f1() {}   // C2251  
void A::B::f1() {}   // OK  
```