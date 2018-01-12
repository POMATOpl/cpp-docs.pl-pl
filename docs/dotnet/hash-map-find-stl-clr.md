---
title: hash_map::Find (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: 53ff8d57-2ea4-485e-9419-aed5e3f5affb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fced245a8a696e104c992c989fb699aa5d28f4c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="hashmapfind-stlclr"></a>hash_map::find (STL/CLR)
Wyszukuje element, który odpowiada określonemu kluczowi.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli co najmniej jednego elementu w kontrolowanej sekwencji ma porządkowanie równoważne z `key`, funkcją członkowską zwracającą iterator wyznaczenie jednego z tych elementów; w przeciwnym razie zwraca [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md) `()`. Umożliwia ona obecnie zlokalizować elementu w kontrolowanej sekwencji zgodny z określonym kluczem.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_map_find.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Myhash_map::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
find A = False  
find b = [b 2]  
find C = False  
```  
  
## <a name="description"></a>Opis  
 Należy pamiętać, że `find` nie gwarantuje, którego element kilka znajdzie.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_map — (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash_map::lower_bound (STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)   
 [hash_map::upper_bound (STL/CLR)](../dotnet/hash-map-upper-bound-stl-clr.md)