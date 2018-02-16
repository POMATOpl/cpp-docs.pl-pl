---
title: ICommandImpl::Execute | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ed92334207c25222eca462876e91137366d4508
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Wykonuje polecenia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Parametry  
 Zobacz [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) w *OLE DB Podręcznik programisty*.  
  
## <a name="remarks"></a>Uwagi  
 Żądany interfejs wychodzących będzie interfejs z obiektu zestawu wierszy, który tworzy tę funkcję.  
  
 **Wykonanie** wywołania [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Zastąp domyślną implementację, aby utworzyć więcej niż jeden zestaw wierszy lub w celu zapewnienia warunki do tworzenia różnych zestawów wierszy.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** atldb.h  
  
## <a name="see-also"></a>Zobacz też  
 [Icommandimpl — klasa](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)