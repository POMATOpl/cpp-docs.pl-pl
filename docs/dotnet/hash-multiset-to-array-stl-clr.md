---
title: hash_multiset::to_array (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: fc28b42a-a8fe-4953-887b-8a12957d4778
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0e06affc46b951e8091615706d0a7c6da276e77d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisettoarray-stlclr"></a>hash_multiset::to_array (STL/CLR)
Kopiuje kontrolowanej sekwencji do nowej tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca tablicę zawierającą kontrolowanej sekwencji. Umożliwia ona uzyskać kopię kontrolowanej sekwencji w postaci tablicy.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multiset_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)