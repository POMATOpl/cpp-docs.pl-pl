---
title: collection_adapter::end (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::collection_adapter::end
dev_langs: C++
helpviewer_keywords: end member [STL/CLR]
ms.assetid: f953a734-2f17-4b68-9ca4-34f980d08887
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c08a9c08ed4fc1ae6501a5c935e769995644eebd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="collectionadapterend-stlclr"></a>collection_adapter::end (STL/CLR)
Określa koniec kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca wejściowych iteratora tego punkty bezpośrednio po zakończeniu kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_collection_adapter_end.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/karty >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [collection_adapter — (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::BEGIN (STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)