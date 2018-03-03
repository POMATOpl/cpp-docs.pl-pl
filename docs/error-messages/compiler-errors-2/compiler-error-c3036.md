---
title: "C3036 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3036
dev_langs:
- C++
helpviewer_keywords:
- C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba560d06e0ee574a3d8145c81ade5cb227e45b99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3036"></a>C3036 błąd kompilatora
"operator": nieprawidłowy token operatora w klauzuli "Reduction" OpenMP  
  
 A [redukcji](../../parallel/openmp/reference/reduction.md) klauzuli nie została poprawnie określona.  
  
 Poniższy przykład generuje C3036:  
  
```  
// C3036.cpp  
// compile with: /openmp  
static float a[1000], b[1000], c[1000];  
void test1(int first, int last) {  
   static float dp = 0.0f;  
   #pragma omp for nowait reduction(.:dp)   // C3036  
   // try the following line instead  
   // #pragma omp for nowait reduction(+: dp)  
   for (int i = first ; i <= last ; ++i)  
      dp += a[i] * b[i];  
}  
```