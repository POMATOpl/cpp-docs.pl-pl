---
title: "Błąd krytyczny C1310 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1310
dev_langs: C++
helpviewer_keywords: C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 05955990b1df5d2e64215a96a5da205d45539bc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1310"></a>Błąd krytyczny C1310
Optymalizacje profilowe z przewodnikiem nie są dostępne z OpenMP  
  
 Nie można połączyć z [/LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md) każdy moduł, który został skompilowany z [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Poniższy przykład generuje C1310:  
  
```  
// C1310.cpp  
// compile with: /openmp /GL /link /LTCG:PGI  
// C1310 expected  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 0; i++)   
         --j;  
   }  
}  
```