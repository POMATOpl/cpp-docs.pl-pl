---
title: hash_multimap::size (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::size
dev_langs: C++
helpviewer_keywords: size member [STL/CLR]
ms.assetid: 6937c980-5952-48bf-b411-81ab03b2f940
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c5fa51ec9a4c439191e3f742374eae973bee9e38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultimapsize-stlclr"></a>hash_multimap::size (STL/CLR)
Liczy liczbę elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca długość kontrolowanej sekwencji. Można użyć do określenia liczby elementów aktualnie w kontrolowanej sekwencji. Jeśli wszystkie najważniejsze informacje dotyczące tego, czy sekwencja ma rozmiar różną od zera, zobacz [hash_multimap::empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multimap_size.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(Myhash_multimap::make_value(L'd', 4));   
    c1.insert(Myhash_multimap::make_value(L'e', 5));   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multimap — (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::EMPTY (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)