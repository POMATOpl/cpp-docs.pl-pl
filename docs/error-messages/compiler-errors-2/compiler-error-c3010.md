---
title: "C3010 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3010
dev_langs: C++
helpviewer_keywords: C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb72ab844831c277271b5f531bd240ed35744d64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3010"></a>C3010 błąd kompilatora
"etykieta": wyskok ze strukturalnego bloku OpenMP jest niedozwolony  
  
 Kod nie można przeskoczyć do lub z bloku OpenMP.  
  
 Poniższy przykład generuje C3010:  
  
```  
// C3010.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
      #pragma omp parallel  
      {  
         goto lbl3;  
      }  
   }  
   lbl3:;   // C3010  
}  
```