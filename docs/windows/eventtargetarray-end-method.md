---
title: "EventTargetArray::End — Metoda | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray::End
dev_langs: C++
helpviewer_keywords: End method
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95c73ed0784b09f56efe817691ba696736b80f20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="eventtargetarrayend-method"></a>EventTargetArray::End — Metoda
Obsługuje infrastrukturę biblioteki WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.  
  
## <a name="syntax"></a>Składnia  
  
```  
ComPtr<IUnknown>* End();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Adres ostatniego elementu w tablicy wewnętrznej procedury obsługi zdarzeń.  
  
## <a name="remarks"></a>Uwagi  
 Pobiera adres ostatniego elementu w tablicy wewnętrznej procedury obsługi zdarzeń.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** event.h  
  
 **Namespace:** Microsoft::wrl:: details —  
  
## <a name="see-also"></a>Zobacz też  
 [Eventtargetarray — klasa](../windows/eventtargetarray-class.md)   
 [Microsoft::wrl:: details — Namespace](../windows/microsoft-wrl-details-namespace.md)