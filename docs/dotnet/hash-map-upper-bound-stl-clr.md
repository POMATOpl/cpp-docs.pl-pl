---
title: hash_map::upper_bound (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_map::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: f83e88b4-e15e-49d5-90e4-cf7360c27c30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 17690c6f99ae8f256003bf54f3bd736f52670e84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="hashmapupperbound-stlclr"></a>hash_map::upper_bound (STL/CLR)
Wyszukuje koniec zakresu, który jest zgodny z określonym kluczem.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska Określa ostatni element `X` w kontrolowanej sekwencji, który tworzy skrót do tego samego zasobnika jako `key` i ma równoważne kolejności do `key`. Jeśli nie zawiera żadnego takiego elementu lub `X` jest ostatniego elementu w kontrolowanej sekwencji zwraca [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`; w przeciwnym razie zwraca określający pierwszy element poza iteratora`X`. Umożliwia ona obecnie Znajdź koniec sekwencję elementów w kontrolowanej sekwencji, który jest zgodny z określonym kluczem.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_map_upper_bound.cpp   
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
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    Myhash_map::iterator it = c1.upper_bound(L'a');   
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.upper_bound(L'b');   
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = [b 2]  
*upper_bound(L'b') = [c 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_map — (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::Count (STL/CLR)](../dotnet/hash-map-count-stl-clr.md)   
 [hash_map::equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash_map::Find (STL/CLR)](../dotnet/hash-map-find-stl-clr.md)   
 [hash_map::lower_bound (STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)