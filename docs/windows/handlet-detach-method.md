---
title: "HandleT::Detach — metoda | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25ee0e3ea826d77795bbdfafda780071d7a817a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="handletdetach-method"></a>HandleT::Detach — Metoda
Usuwa skojarzenia bieżącego obiektu handlet — z uchwytu podstawowej.  
  
## <a name="syntax"></a>Składnia  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Dojście podstawowej.  
  
## <a name="remarks"></a>Uwagi  
 Po zakończeniu tej operacji, bieżący handlet — ustawiono nieprawidłowy stan.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: wrappers —  
  
## <a name="see-also"></a>Zobacz też  
 [HandleT, klasa](../windows/handlet-class.md)