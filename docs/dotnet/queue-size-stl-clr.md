---
title: Queue::size (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 864510ef-5a00-4377-b286-1e73f237e359
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1cd490cb51308bfd3b9b2fb62a8e5d580249cce9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161216"
---
# <a name="queuesize-stlclr"></a>queue::size (STL/CLR)
Liczy liczbę elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca długość kontrolowanej sekwencji. Można użyć do określenia liczby elementów aktualnie w kontrolowanej sekwencji. Jeśli wszystkie najważniejsze informacje dotyczące tego, czy sekwencja ma rozmiar różną od zera, zobacz [queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
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
 a b c  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [kolejki (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)