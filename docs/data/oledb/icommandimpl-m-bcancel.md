---
title: ICommandImpl::m_bCancel | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
dev_langs:
- C++
helpviewer_keywords:
- m_bCancel
ms.assetid: f3b6fb60-4de4-4d81-a5d2-4052c41be0de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5304ba202160e9692eb5a3bc8cb11b5ab9267a72
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimplmbcancel"></a>ICommandImpl::m_bCancel
Wskazuje, czy polecenie zostało anulowane.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
unsigned m_bCancel:1;  
  
```  
  
## <a name="remarks"></a>Uwagi  
 Można pobrać zmiennej w **Execute** metody klasy poleceń i Anuluj zależnie od potrzeb.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Icommandimpl — klasa](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)