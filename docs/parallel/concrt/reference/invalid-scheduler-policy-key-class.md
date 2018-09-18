---
title: invalid_scheduler_policy_key — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e7dc90ce1ff04d3d02aed13927f137a2b4f7f75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113295"
---
# <a name="invalidschedulerpolicykey-class"></a>invalid_scheduler_policy_key — Klasa
Ta klasa opisuje wyjątek generowany, gdy nieprawidłową lub nieznany klucz zostanie przekazany do `SchedulerPolicy` konstruktora obiektu lub `SetPolicyValue` metody `SchedulerPolicy` obiekt jest przekazywany klucza, które należy zmienić przy użyciu innych metod, takich jak `SetConcurrencyLimits` metody.  
  
## <a name="syntax"></a>Składnia  
  
```
class invalid_scheduler_policy_key : public std::exception;
```  
  
## <a name="members"></a>Elementy członkowskie  
  
### <a name="public-constructors"></a>Konstruktory publiczne  
  
|Nazwa|Opis|  
|----------|-----------------|  
|[invalid_scheduler_policy_key](#ctor)|Przeciążone. Konstruuje `invalid_scheduler_policy_key` obiektu.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** concrt.h  
  
 **Namespace:** współbieżności  
  
##  <a name="ctor"></a> invalid_scheduler_policy_key 

 Konstruuje `invalid_scheduler_policy_key` obiektu.  
  
```
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```  
  
### <a name="parameters"></a>Parametry  
*_Message*<br/>
Opisowy komunikat dotyczący błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [Współbieżność Namespace](concurrency-namespace.md)   
 [SchedulerPolicy, klasa](schedulerpolicy-class.md)
