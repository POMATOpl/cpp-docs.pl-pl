---
title: "ChainInterfaces::CastToUnknown — metoda | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f49ca9eb6218e5dce42be5d951d134ad74745e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfacescasttounknown-method"></a>ChainInterfaces::CastToUnknown — Metoda
Rzutuje wskaźnik interfejsu z typem zdefiniowanym przez `I0` parametr szablonu na wskaźnik do elementu IUnknown.  
  
## <a name="syntax"></a>Składnia  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Wskaźnik do elementu IUnknown.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** implements.h  
  
 **Namespace:** Microsoft::wrl —  
  
## <a name="see-also"></a>Zobacz też  
 [ChainInterfaces, struktura](../windows/chaininterfaces-structure.md)