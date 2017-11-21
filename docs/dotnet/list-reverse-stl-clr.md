---
title: list::reverse (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::reverse
dev_langs: C++
helpviewer_keywords: reverse member [STL/CLR]
ms.assetid: de3bce1e-01fe-461d-a785-5cf4fcea988f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0c8702ff0438fe9a22de0c7b079d757e9a8d66d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="listreverse-stlclr"></a>list::reverse (STL/CLR)
Odwraca kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
void reverse();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska Odwraca kolejność wszystkich elementów w kontrolowanej sekwencji. Służy do uwzględnienia listy elementów.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_list_reverse.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// reverse and redisplay   
    c1.reverse();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/listy >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Lista (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)