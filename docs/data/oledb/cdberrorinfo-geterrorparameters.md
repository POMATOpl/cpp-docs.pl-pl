---
title: CDBErrorInfo::GetErrorParameters | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
dev_langs:
- C++
helpviewer_keywords:
- GetErrorParameters method
ms.assetid: 3a2dd8e2-fecc-4315-9f2b-ce3138cdd187
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 703de648f78111c3fd14f214c19571ac40d4bc63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfogeterrorparameters"></a>CDBErrorInfo::GetErrorParameters
Wywołania [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) do zwrócenia parametry błędów.  
  
## <a name="syntax"></a>Składnia  
  
```
HRESULT GetErrorParameters(ULONG ulRecordNum,   
  DISPPARAMS* pdispparams) const throw();  
```  
  
#### <a name="parameters"></a>Parametry  
 Zobacz [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) w *OLE DB Podręcznik programisty*.  
  
## <a name="return-value"></a>Wartość zwracana  
 Standard `HRESULT`.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldbcli.h  
  
## <a name="see-also"></a>Zobacz też  
 [CDBErrorInfo, klasa](../../data/oledb/cdberrorinfo-class.md)