---
title: BLOB_ENTRY | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BLOB_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY macro
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ca27d4dffccdf644aec5f28d2523cebcd374f24
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="blobentry"></a>BLOB_ENTRY
Używane z `BEGIN_COLUMN_MAP` i `END_COLUMN_MAP` powiązać dużego obiektu binarnego ([obiektu BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)).  
  
## <a name="syntax"></a>Składnia  
  
```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `nOrdinal`  
 [in] Numer kolumny.  
  
 *IID*  
 [in] Interfejs identyfikatora GUID, takich jak **IDD_ISequentialStream**, używana do pobrania obiektu BLOB.  
  
 `flags`  
 [in] Tryb przechowywania flagi zgodnie z definicją w modelu OLE strukturalnego magazynu (na przykład **STGM_READ**).  
  
 `data`  
 [in] Odpowiedni element członkowski danych w rekordzie użytkownika.  
  
## <a name="example"></a>Przykład  
 Zobacz [sposób pobierania obiektu BLOB?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldbcli.h  
  
## <a name="see-also"></a>Zobacz też  
 [Makra i funkcje globalne dla szablonów konsumentów OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY —](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)