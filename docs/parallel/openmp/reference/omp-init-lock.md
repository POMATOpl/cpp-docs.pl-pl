---
title: omp_init_lock | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_init_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_init_lock OpenMP function
ms.assetid: 7a65e3e2-2e31-4645-964c-c1e82e2a4d0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f07e542f9c850b300ab55cbbbbb0155173eda98f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="ompinitlock"></a>omp_init_lock
Inicjuje proste blokady.  
  
## <a name="syntax"></a>Składnia  
  
```  
void omp_init_lock(  
   omp_lock_t *lock  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `lock`  
 Zmienna typu [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md).  
  
## <a name="remarks"></a>Uwagi  
 Aby uzyskać więcej informacji, zobacz [3.2.1 funkcje omp_init_lock i omp_init_nest_lock](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).  
  
## <a name="example"></a>Przykład  
  
```  
// omp_init_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t my_lock;  
  
int main() {  
   omp_init_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num( );  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_lock(&my_lock);  
         printf_s("Thread %d - starting locked region\n", tid);  
         printf_s("Thread %d - ending locked region\n", tid);  
         omp_unset_lock(&my_lock);  
      }  
   }  
  
   omp_destroy_lock(&my_lock);  
}  
```  
  
```Output  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje](../../../parallel/openmp/reference/openmp-functions.md)