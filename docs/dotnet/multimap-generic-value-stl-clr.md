---
title: multimap::generic_value (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: e403233f-5132-45ca-be04-2c85e923f37d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0a0febedc05b0d40b6d92a8c20e3b527f913e642
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="multimapgenericvalue-stlclr"></a>multimap::generic_value (STL/CLR)
Typ elementu do użytku ogólnego interfejs dla kontenera.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano typu obiektu `GValue` opisujący wartość elementu przechowywane do użytku ogólnego interfejs dla tej klasy kontenera szablonu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_multimap_generic_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultimap::generic_container^ gc1 = %c1;   
    for each (Mymultimap::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultimap::generic_iterator gcit = gc1->begin();   
    Mymultimap::generic_value gcval = *gcit;   
    System::Console::WriteLine(" [{0} {1}]", gcval->first, gcval->second);   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
[a 1]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::generic_container (STL/CLR)](../dotnet/multimap-generic-container-stl-clr.md)   
 [multimap::generic_iterator (STL/CLR)](../dotnet/multimap-generic-iterator-stl-clr.md)   
 [multimap::generic_reverse_iterator (STL/CLR)](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)