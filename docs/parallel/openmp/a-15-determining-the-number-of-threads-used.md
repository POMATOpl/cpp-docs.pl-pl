---
title: A.15 określającą liczbę wątków używanych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b50858a3384fa5f8d867f13a699e1fc271c101ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686389"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Określanie liczby wykorzystywanych wątków
Rozważmy następujący przykład niepoprawne (dla [sekcji 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) na stronie 37):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()` Wywołanie zwraca wartość 1 w serial sekcji kodu, więc *potoki* będzie zawsze równa 1 w poprzednim przykładzie. Aby ustalić liczbę wątków, które zostaną wdrożone do równoległego regionu, wywołanie powinien znajdować się wewnątrz równoległego regionu.  
  
 Poniższy przykład przedstawia sposób ponownego zapisywania tego programu, bez uwzględniania zapytanie to liczba wątków:  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```