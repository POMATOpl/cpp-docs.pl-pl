---
title: "C3046 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3046
dev_langs: C++
helpviewer_keywords: C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49249bcf8b0455efea0e5dfad62d263ade2a0368
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3046"></a>C3046 błąd kompilatora
Brak bloku strukturalnego w regionie "#pragma omp sections" OpenMP  
  
 A [sekcje](../../parallel/openmp/reference/sections-openmp.md) dyrektywy ma blok kodu puste.  
  
 Poniższy przykład generuje C3046:  
  
```  
// C3046.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
/*  
         ++n2;  
  
         #pragma omp section  
         {  
            ++n3;  
         }  
*/  
       }   // C3046 uncomment code to resolve this C3046  
   }  
}  
```