---
title: firstprivate | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 10b5a270feb638a98c060b58e90af8146ff97325
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="firstprivate"></a>firstprivate
Określa, że każdy wątek powinien mieć własne wystąpienie zmiennej i czy zmienna powinien być inicjowany przez wartość zmiennej, ponieważ istnieje przed równoległych konstrukcji.  
  
## <a name="syntax"></a>Składnia  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`var`|Zmienna wystąpień w każdy wątek, który zostanie zainicjowana wartość zmiennej, ponieważ istnieje przed równoległych konstrukcji. Jeśli określono więcej niż jednej zmiennej, oddziel przecinkami nazwy zmiennych.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="remarks"></a>Uwagi  
 `firstprivate` ma zastosowanie do następujących dyrektyw:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Sekcje](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 Aby uzyskać więcej informacji, zobacz [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).  
  
## <a name="example"></a>Przykład  
 Na przykład za pomocą `firstprivate`, zapoznaj się z przykładem w [prywatnej](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Klauzule](../../../parallel/openmp/reference/openmp-clauses.md)