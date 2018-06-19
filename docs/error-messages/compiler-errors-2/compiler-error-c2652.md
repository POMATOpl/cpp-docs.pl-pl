---
title: C2652 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 576aef31268c0cdce09162fc367358e0ed044429
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232202"
---
# <a name="compiler-error-c2652"></a>C2652 błąd kompilatora
"identyfikator": niedozwolony Konstruktor kopiujący: pierwszy parametr nie może być identyfikator  
  
 Pierwszy parametr w Konstruktor kopiujący ma taki sam typ jak klasy, struktury lub Unii, dla którego jest zdefiniowany. Pierwszy parametr może być odwołaniem do typu, ale nie samego typu.  
  
 Poniższy przykład generuje C2651:  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```