---
title: priority_queue::generic_value (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::generic_value
dev_langs: C++
helpviewer_keywords: generic_value member [STL/CLR]
ms.assetid: d534e95b-7939-4fb4-bb71-2164e2b97c4f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 19ebfefefcc3827fb632654e39a865449b3cf675
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuegenericvalue-stlclr"></a>priority_queue::generic_value (STL/CLR)
Typ elementu do użytku ogólnego interfejs dla kontenera.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano typu obiektu `GValue` opisujący wartość elementu przechowywane do użytku ogólnego interfejs dla tej klasy kontenera szablonu. (`GValue` jest `value_type` lub `value_type^` Jeśli `value_type` jest typu referencyjnego.)  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_priority_queue_generic_value.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in priority order using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mypriority_queue::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
c b a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [priority_queue — (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)