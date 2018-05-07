---
title: hash_multiset::reverse_iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- reverse_iterator member [STL/CLR]
ms.assetid: a988adca-8fd7-4678-9edc-041555a3561d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 67a3e2c36ca580605ea5a87987d33e58b60979e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetreverseiterator-stlclr"></a>hash_multiset::reverse_iterator (STL/CLR)
Typ odwrotnej iteratora w kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef T3 reverse_iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ zawiera opis obiektu nieokreślonego typu `T3` który może służyć jako odwrotnej iteratora w kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multiset_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Myhash_multiset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multiset — (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::const_iterator (STL/CLR)](../dotnet/hash-multiset-const-iterator-stl-clr.md)   
 [hash_multiset::const_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)   
 [hash_multiset::iterator (STL/CLR)](../dotnet/hash-multiset-iterator-stl-clr.md)