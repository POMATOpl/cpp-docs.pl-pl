---
title: priority_queue::size (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 37ef4be3-daac-4b5a-9a00-085863f694e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c399a6154034623d8695d75c0f6314bffbce712
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="priorityqueuesize-stlclr"></a>priority_queue::size (STL/CLR)
Liczy liczbę elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca długość kontrolowanej sekwencji. Można użyć do określenia liczby elementów aktualnie w kontrolowanej sekwencji. Jeśli wszystkie najważniejsze informacje dotyczące tego, czy sekwencja ma rozmiar różną od zera, zobacz [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_priority_queue_size.cpp   
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
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [priority_queue — (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)