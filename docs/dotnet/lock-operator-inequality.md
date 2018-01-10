---
title: "Lock::operator — wartość! = | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs: C++
helpviewer_keywords: lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7285a974b788fd2f6e885a67dab9257a83886d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="lockoperator"></a>lock::operator!=
Operator nierówności.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `t`  
 Obiekt do porównania pod kątem nierówności.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca `true` Jeśli `t` różni się od obiektu blokady `false` inaczej.  
  
## <a name="example"></a>Przykład  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
```Output  
Inequal!  
```  
  
## <a name="requirements"></a>Wymagania  
 **Plik nagłówka** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Zobacz też  
 [elementy członkowskie Lock](../dotnet/lock-members.md)   
 [lock::operator==](../dotnet/lock-operator-equality.md)