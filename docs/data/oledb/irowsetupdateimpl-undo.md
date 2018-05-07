---
title: IRowsetUpdateImpl::Undo | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
dev_langs:
- C++
helpviewer_keywords:
- Undo method
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d98465d396084c157c40bdca41c3daac46bc4ad7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimplundo"></a>IRowsetUpdateImpl::Undo
Umożliwia cofnięcie zmian do wiersza od czasu ostatniego pobrania lub aktualizacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hReserved`  
 [in] Odpowiada `hChapter` parametru w [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 [out] Odpowiada `pcRows` parametru w [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 [in] Odpowiada *prgRows* parametru w [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 Dla innych parametrów, zobacz [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx) w *OLE DB Podręcznik programisty*.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [IRowsetUpdateImpl, klasa](../../data/oledb/irowsetupdateimpl-class.md)