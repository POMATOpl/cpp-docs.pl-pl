---
title: "Przy użyciu threadprivate dyrektywy A.26 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6eda76c2-c4f1-4208-a900-e0ea98a53eca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1337405fc433ccfc609756cd83ff9e38eb55a79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="a26---using-the-threadprivate-directive"></a>A.26   Użycie dyrektywy prywatnego wątku
W poniższych przykładach pokazano, jak używać `threadprivate` — dyrektywa ([sekcji 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) na stronie 23) umożliwiają każdy wątek oddzielne licznika.  
  
 **Przykład 1:**  
  
```  
int counter = 0;  
#pragma omp threadprivate(counter)  
  
int sub()  
{  
    counter++;  
    return(counter);  
}  
```  
  
 **Przykład 2:**  
  
```  
int sub()  
{  
    static int counter = 0;  
    #pragma omp threadprivate(counter)  
    counter++;  
    return(counter);  
}  
```