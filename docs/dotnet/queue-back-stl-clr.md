---
title: Queue::back (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::back
dev_langs: C++
helpviewer_keywords: back member [STL/CLR]
ms.assetid: 983a5c0f-0a2f-475f-932b-e7dec9eaffbb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6badb225d57295931aac7ba6fe6d6e6ec747f6e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="queueback-stlclr"></a>queue::back (STL/CLR)
Uzyskuje dostęp do ostatniego elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
reference back();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca odwołanie do ostatniego elementu w kontrolowanej sekwencji musi być niepusta. Umożliwia ona dostęp do ostatniego elementu, gdy wiesz, że istnieje.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_queue_back.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [kolejki (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)   
 [Queue::Front (STL/CLR)](../dotnet/queue-front-stl-clr.md)   
 [Queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)