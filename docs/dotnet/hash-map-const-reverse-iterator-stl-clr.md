---
title: hash_map::const_reverse_iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::const_reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_reverse_iterator member [STL/CLR]
ms.assetid: 0c31131a-6eb6-4b14-bab9-ebc8ff25f414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e513528be774089039b6666dd0f03edfbf29042e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapconstreverseiterator-stlclr"></a>hash_map::const_reverse_iterator (STL/CLR)
Typ stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ zawiera opis obiektu nieokreślonego typu `T4` który może służyć jako stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_map_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_map::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" [{0} {1}]", crit->first, crit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[c 3] [b 2] [a 1]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_map — (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::reverse_iterator (STL/CLR)](../dotnet/hash-map-reverse-iterator-stl-clr.md)