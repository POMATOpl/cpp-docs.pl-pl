---
title: ClassFactory::AddRef, metoda | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method
ms.assetid: 5b091785-dea4-42b6-a502-0db5fc7a5a2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 276024be7b3d75edf308e43a08e4d2cbe9901c1e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652058"
---
# <a name="classfactoryaddref-method"></a>ClassFactory::AddRef — Metoda
Zwiększa liczbę odwołań dla bieżącego **ClassFactory —** obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 S_OK w przypadku powodzenia; w przeciwnym razie wartość HRESULT, który opisuje błąd.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Zobacz też  
 [ClassFactory, klasa](../windows/classfactory-class.md)