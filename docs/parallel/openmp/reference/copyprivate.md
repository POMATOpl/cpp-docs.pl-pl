---
title: copyprivate | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyprivate
dev_langs: C++
helpviewer_keywords: copyprivate OpenMP clause
ms.assetid: 02c0209d-abe8-4797-8365-a82b53c3f15d
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ecbfa14b40a219d626293eff9fb602673bc194a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="copyprivate"></a>copyprivate
Określa, że co najmniej jedną zmienną powinna być współużytkowane przez wszystkie wątki.  
  
## <a name="syntax"></a>Składnia  
  
```  
copyprivate(var)  
```  
  
## <a name="remarks"></a>Uwagi  
 w przypadku gdy  
  
 `var`  
 Co najmniej jedną zmienną do udostępniania. Jeśli określono więcej niż jednej zmiennej, oddziel przecinkami nazwy zmiennych.  
  
## <a name="remarks"></a>Uwagi  
 `copyprivate`dotyczy [pojedynczego](../../../parallel/openmp/reference/single.md) dyrektywy.  
  
 Aby uzyskać więcej informacji, zobacz [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md).  
  
## <a name="example"></a>Przykład  
  
```  
// omp_copyprivate.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
float x, y, fGlobal = 1.0;  
#pragma omp threadprivate(x, y)  
  
float get_float() {  
   fGlobal += 0.001;  
   return fGlobal;  
}  
  
void use_float(float f, int t) {  
   printf_s("Value = %f, thread = %d\n", f, t);  
}  
  
void CopyPrivate(float a, float b) {  
   #pragma omp single copyprivate(a, b, x, y)   
   {  
      a = get_float();  
      b = get_float();  
      x = get_float();  
      y = get_float();  
    }  
  
   use_float(a, omp_get_thread_num());     
   use_float(b, omp_get_thread_num());     
   use_float(x, omp_get_thread_num());  
   use_float(y, omp_get_thread_num());  
}  
  
int main() {  
   float a = 9.99, b = 123.456;  
  
   printf_s("call CopyPrivate from a single thread\n");  
   CopyPrivate(9.99, 123.456);  
  
   printf_s("call CopyPrivate from a parallel region\n");  
   #pragma omp parallel       
   {  
      CopyPrivate(a, b);  
   }  
}  
```  
  
```Output  
call CopyPrivate from a single thread  
Value = 1.001000, thread = 0  
Value = 1.002000, thread = 0  
Value = 1.003000, thread = 0  
Value = 1.004000, thread = 0  
call CopyPrivate from a parallel region  
Value = 1.005000, thread = 0  
Value = 1.005000, thread = 1  
Value = 1.006000, thread = 0  
Value = 1.006000, thread = 1  
Value = 1.007000, thread = 0  
Value = 1.007000, thread = 1  
Value = 1.008000, thread = 0  
Value = 1.008000, thread = 1  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Klauzule](../../../parallel/openmp/reference/openmp-clauses.md)