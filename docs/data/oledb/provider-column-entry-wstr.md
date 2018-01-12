---
title: PROVIDER_COLUMN_ENTRY_WSTR | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_WSTR
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_WSTR macro
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c3d080707ebe1eb9ecfd76189b1d76be76c9c71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="providercolumnentrywstr"></a>PROVIDER_COLUMN_ENTRY_WSTR
Przedstawia kolumnę określonych obsługiwane przez dostawcę.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
PROVIDER_COLUMN_ENTRY_WSTR(  
name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Parametry  
 *Nazwa*  
 [in] Nazwa kolumny.  
  
 `ordinal`  
 [in] Numer kolumny. Jeśli kolumna jest kolumną zakładki, numer kolumny nie może być 0.  
  
 `member`  
 [in] Zmiennej członkowskiej klasy danych, która przechowuje dane.  
  
## <a name="remarks"></a>Uwagi  
 Używanie tego makra, gdy kolumna danych jest zakończony znakiem null ciągu znaków Unicode, [DBTYPE_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Makra dla szablonów dostawców OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Szablony dostawców OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)