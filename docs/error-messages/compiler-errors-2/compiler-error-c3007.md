---
title: "C3007 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3007
dev_langs: C++
helpviewer_keywords: C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1342cd9f028987ec33659e6bc3b7e7020e0979a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3007"></a>C3007 błąd kompilatora
"argument": klauzula w dyrektywie OpenMP "dyrektywy" nie przyjmuje argumentu  
  
 OpenMP — dyrektywa były argumentu, ale dyrektywy nie przyjmuje argumentu.  
  
 Poniższy przykład generuje C3007:  
  
```  
// C3007.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel for ordered(2)   // C3007  
}  
```