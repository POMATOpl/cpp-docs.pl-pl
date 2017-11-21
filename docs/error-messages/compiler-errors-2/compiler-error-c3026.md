---
title: "C3026 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3026
dev_langs: C++
helpviewer_keywords: C3026
ms.assetid: 3297060e-cc5b-4600-a2db-09bfc4ffa21f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3953553c8af6da98812c228f4b0bbf8c9428947d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3026"></a>C3026 błąd kompilatora
"klauzuli": stałe wyrażenie musi być dodatnią  
  
 Klauzula przekazano wartość całkowitą, ale wartość nie jest liczbą dodatnią. Liczba musi być dodatnia.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3026:  
  
```  
// C3026.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main()  
{  
    int i;  
    const int i1 = 0;  
  
    #pragma omp parallel for num_threads(i1)   // C3026  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    #pragma omp parallel for num_threads(i1 + 1)   // OK  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
}  
```