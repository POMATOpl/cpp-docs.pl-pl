---
title: PROVIDER_COLUMN_ENTRY | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY macro
ms.assetid: 7921cfc1-aa9c-493e-8fc4-9d4294cafe72
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9e91df6d8598e59fc2b0bd19cd075ca3cf41a65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="providercolumnentry"></a>PROVIDER_COLUMN_ENTRY
Przedstawia kolumnę określonych obsługiwane przez dostawcę.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
PROVIDER_COLUMN_ENTRY (  
name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Parametry  
 *Nazwa*  
 [in] Nazwa kolumny.  
  
 `ordinal`  
 [in] Numer kolumny. Jeśli kolumna jest kolumną zakładki, numer kolumny nie może być 0.  
  
 `member`  
 [in] Zmiennej członkowskiej w `dataClass` odpowiadające kolumnie.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Makra dla szablonów dostawców OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Szablony dostawców OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)