---
title: scheduler_interface — struktura | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b06b270c4971239b91fa81b9ad35d8fef52b7e76
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="schedulerinterface-structure"></a>scheduler_interface — Struktura
Interfejs harmonogramu  
  
## <a name="syntax"></a>Składnia  
  
```
struct __declspec(novtable) scheduler_interface;
```  
  
## <a name="members"></a>Elementy członkowskie  
  
### <a name="public-methods"></a>Metody publiczne  
  
|Nazwa|Opis|  
|----------|-----------------|  
|[scheduler_interface::schedule](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia  
 `scheduler_interface`  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** pplinterface.h  
  
 **Namespace:** współbieżności  
  
##  <a name="schedule"></a>  scheduler_interface::Schedule — metoda  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>Zobacz też  
 [Przestrzeń nazw współbieżności](concurrency-namespace.md)
