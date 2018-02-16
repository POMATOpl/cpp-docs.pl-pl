---
title: "Cdataconnection::operator — wartość logiczna (OLE DB) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: e0791faf-2ed2-4dbb-9e68-3b9b5da2b7a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5a3d8317df5d7ed4d034b2d16b9d282aab08f848
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-bool-ole-db"></a>CDataConnection::operator bool (OLE DB)
Określa, czy bieżąca sesja jest otwarty.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
operator bool() throw();  
  
```  
  
## <a name="remarks"></a>Uwagi  
 Zwraca `bool` wartość (C++ typu danych). **wartość true,** oznacza, że bieżąca sesja jest otwarty; **false** oznacza, że bieżąca sesja jest zamknięty.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldbcli.h  
  
## <a name="see-also"></a>Zobacz też  
 [Cdataconnection — klasa](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator, wartość logiczna](../../data/oledb/cdataconnection-operator-bool.md)