---
title: AsyncBase::ErrorCode — metoda | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abd3eae18d793739866b6c0dd8a1b6a994093c93
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2018
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
 [AsyncBase, klasa](../windows/asyncbase-class.md)