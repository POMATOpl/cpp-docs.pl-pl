---
title: hash_multimap::const_reverse_iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::const_reverse_iterator
dev_langs: C++
helpviewer_keywords: const_reverse_iterator member [STL/CLR]
ms.assetid: 060a2bba-6d63-48ce-a8f7-deb061dfd489
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: db4bf4914bffdbc0954fedff67a6f23edbf4927e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimapconstreverseiterator-stlclr"></a>hash_multimap::const_reverse_iterator (STL/CLR)
Typ stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ zawiera opis obiektu nieokreślonego typu `T4` który może służyć jako stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multimap_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_multimap::const_reverse_iterator crit = c1.rbegin();   
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
 [hash_multimap — (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::reverse_iterator (STL/CLR)](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)