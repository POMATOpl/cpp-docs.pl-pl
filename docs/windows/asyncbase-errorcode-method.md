---
title: "AsyncBase::ErrorCode — metoda | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs: C++
helpviewer_keywords: ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2aa8e137d1282f2a1e46a017192d213781e89090
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseerrorcode-method"></a>AsyncBase::ErrorCode — Metoda
Pobiera kod błędu dla bieżącej operacji asynchronicznej.  
  
## <a name="syntax"></a>Składnia  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `error`  
 Lokalizacja, w której przechowuje bieżącego kodu błędu w tej operacji.  
  
## <a name="remarks"></a>Uwagi  
 Ta operacja jest bezpieczne wątkowo.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** async.h  
  
 **Namespace:** Microsoft::wrl —  
  
## <a name="see-also"></a>Zobacz też  
 [Asyncbase — klasa](../windows/asyncbase-class.md)