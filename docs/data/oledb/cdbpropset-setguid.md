---
title: CDBPropSet::SetGUID | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 140bc76968780efff826ccc42343f27b2cd2eae6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094003"
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
Ustawia **guidPropertySet** w **DBPROPSET** struktury.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parametry  
 `guid`  
 [in] Identyfikator GUID używany do ustawiania **guidPropertySet** pole [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) struktury.  
  
## <a name="remarks"></a>Uwagi  
 W tym polu można wprowadzić przez [Konstruktor](../../data/oledb/cdbpropset-cdbpropset.md) również.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldbcli.h  
  
## <a name="see-also"></a>Zobacz też  
 [CDBPropSet, klasa](../../data/oledb/cdbpropset-class.md)