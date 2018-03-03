---
title: "AsyncBase::Start — metoda | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 419cbec3500977ec5dbeb063e444c1fced8783aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start — Metoda
Rozpoczyna operację asynchroniczną.  
  
## <a name="syntax"></a>Składnia  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 S_OK, jeśli operacja rozpoczyna się lub jest już uruchomiona; w przeciwnym razie E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Uwagi  
 Start() jest domyślna implementacja elementu IAsyncInfo::Start, a nie rzeczywiste działa. Uruchamia operację asynchroniczną, przesłonić metodę wirtualną czysty OnStart().  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** async.h  
  
 **Namespace:** Microsoft::wrl —  
  
## <a name="see-also"></a>Zobacz też  
 [AsyncBase, klasa](../windows/asyncbase-class.md)