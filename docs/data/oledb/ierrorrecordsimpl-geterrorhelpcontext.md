---
title: IErrorRecordsImpl::GetErrorHelpContext | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
dev_langs: C++
helpviewer_keywords: GetErrorHelpContext method
ms.assetid: 53d70239-0d64-482e-9ad4-4e1f4f02d5a3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2167384aca71a8bcd95240b007f84dbea6a498fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="ierrorrecordsimplgeterrorhelpcontext"></a>IErrorRecordsImpl::GetErrorHelpContext
Pobiera identyfikator kontekstu pomocy z rekord błędu.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
      DWORD GetErrorHelpContext(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rCurError`  
 `ERRORINFO` Rekordów w **IErrorInfo** interfejsu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Identyfikator kontekstu pomocy dla błędu.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Ierrorrecordsimpl — klasa](../../data/oledb/ierrorrecordsimpl-class.md)