---
title: IRowsetImpl::GetNextRows | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
dev_langs: C++
helpviewer_keywords: GetNextRows method
ms.assetid: 1c0975d6-d770-4884-830b-6986c6fa8e65
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c4bada3de31e6e856f29d5a930bb94ec5d8b038
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplgetnextrows"></a>IRowsetImpl::GetNextRows
Pobiera wiersze po kolei, pamiętaj o tym poprzedniej pozycji.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
      STDMETHOD( GetNextRows )(  
   HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 Zobacz [IRowset::GetNextRows](https://msdn.microsoft.com/en-us/library/ms709827.aspx) w *OLE DB Podręcznik programisty*.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Irowsetimpl — klasa](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)   
 [IRowsetImpl::ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)