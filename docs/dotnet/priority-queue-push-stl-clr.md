---
title: priority_queue::push (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::push
dev_langs:
- C++
helpviewer_keywords:
- push member [STL/CLR]
ms.assetid: 317d3feb-0688-4658-866b-a26cae060354
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7402af9a18f3d0f2f9f434393f5645d4267bb5b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="priorityqueuepush-stlclr"></a>priority_queue::push (STL/CLR)
Dodaje nowy element.  
  
## <a name="syntax"></a>Składnia  
  
```  
void push(value_type val);  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska wstawia element z wartością `val` w kontrolowanej sekwencji i zmienia kolejność kontrolowanej sekwencji do obsługi dyscypliny stosu. Umożliwia ona Dodaj inny element w kolejce.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_priority_queue_push.cpp   
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
 [priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)