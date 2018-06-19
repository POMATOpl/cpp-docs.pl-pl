---
title: hash_multimap::mapped_type (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::mapped_type
dev_langs:
- C++
helpviewer_keywords:
- mapped_type member [STL/CLR]
ms.assetid: b97db6a7-9d4e-42f0-a725-ac309f5374bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cafb9c8b860571e18cd21049e4a208c27d59ad75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108215"
---
# <a name="hashmultimapmappedtype-stlclr"></a>hash_multimap::mapped_type (STL/CLR)
Typ mapowanej wartości skojarzonej z poszczególnymi kluczami.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef Mapped mapped_type;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ jest synonimem parametru szablonu `Mapped`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multimap_mapped_type.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using mapped_type   
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in mapped_type object   
        Myhash_multimap::mapped_type val = it->second;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
1 2 3  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multimap — (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::key_compare (STL/CLR)](../dotnet/hash-multimap-key-compare-stl-clr.md)   
 [hash_multimap::value_type (STL/CLR)](../dotnet/hash-multimap-value-type-stl-clr.md)