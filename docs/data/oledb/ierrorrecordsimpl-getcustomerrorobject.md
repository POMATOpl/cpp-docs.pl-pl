---
title: IErrorRecordsImpl::GetCustomErrorObject | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
dev_langs:
- C++
helpviewer_keywords:
- GetCustomErrorObject method
ms.assetid: 96d3549b-a49c-4552-94b2-71babaf1bf20
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb2435c62030e7dd187ee3ad6d0164396b809ddf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="ierrorrecordsimplgetcustomerrorobject"></a>IErrorRecordsImpl::GetCustomErrorObject
Zwraca wskaźnik do interfejsu w obiekcie błędu niestandardowego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
      STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>Parametry  
 Zobacz [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) w *OLE DB Podręcznik programisty*.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [IErrorRecordsImpl, klasa](../../data/oledb/ierrorrecordsimpl-class.md)