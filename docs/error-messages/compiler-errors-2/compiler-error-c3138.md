---
title: C3138 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3138
dev_langs:
- C++
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad98c034e3de791da6948d5c08c8cd72c0c681f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3138"></a>C3138 błąd kompilatora
"interface": interfejs 'attribute' musi dziedziczyć z IDispatch lub interfejsu, który dziedziczy z IDispatch  
  
 Interfejs o [podwójną](../../windows/dual.md) lub [dispinterface](../../windows/dispinterface.md) nie ma atrybutów `IDispatch` jako bezpośrednie lub pośrednie interfejs podstawowy.  
  
 Poniższy przykład generuje C3138:  
  
```  
// C3138.cpp  
#include <unknwn.h>  
  
[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyCustomInterface  
{  
   HRESULT mf1(void);  
};  
  
[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyDispInterface : IUnknown  
{  
   [id(1)] HRESULT mf2(void);  
};  
  
[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected  
{  
   HRESULT mf3(void);  
};  
```