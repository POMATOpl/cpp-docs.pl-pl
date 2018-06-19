---
title: priority_queue::get_container (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::get_container
dev_langs:
- C++
helpviewer_keywords:
- get_container member [STL/CLR]
ms.assetid: bd3cc63b-776f-495c-bf81-a9e8ba189a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5bb6ca83c8be9e1ab7b39a0f3552adc2ebaafa17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159135"
---
# <a name="priorityqueuegetcontainer-stlclr"></a>priority_queue::get_container (STL/CLR)
Uzyskuje dostęp do podstawowych kontenera.  
  
## <a name="syntax"></a>Składnia  
  
```  
container_type get_container();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca podstawowej kontenera. Umożliwia ona obejścia ograniczenia narzucone przez otoki kontenera.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_priority_queue_get_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [priority_queue — (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)