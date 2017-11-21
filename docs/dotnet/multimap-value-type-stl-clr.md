---
title: multimap::value_type (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: c10d75f9-2efe-41f7-babc-655c68c14a4f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4e5413f692555910cbdeafe8721eb7b2caa2f757
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="multimapvaluetype-stlclr"></a>multimap::value_type (STL/CLR)
Typ elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef generic_value value_type;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ jest synonimem `generic_value`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_multimap_value_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using value_type   
    for (Mymultimap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mymultimap::value_type val = *it;   
        System::Console::Write(" [{0} {1}]", val->first, val->second);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::const_reference (STL/CLR)](../dotnet/multimap-const-reference-stl-clr.md)   
 [multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)   
 [multimap::Reference (STL/CLR)](../dotnet/multimap-reference-stl-clr.md)