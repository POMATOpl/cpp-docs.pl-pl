---
title: hash_map::to_array (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: 26d7620f-893b-47f2-99e3-f0b6af3aedc9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76e6d4c11473fd78a8dcb41afb4c7726f70afe15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106170"
---
# <a name="hashmaptoarray-stlclr"></a>hash_map::to_array (STL/CLR)
Kopiuje kontrolowanej sekwencji do nowej tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca tablicę zawierającą kontrolowanej sekwencji. Umożliwia ona uzyskać kopię kontrolowanej sekwencji w postaci tablicy.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_map_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Myhash_map::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Myhash_map::make_value(L'd', 4));   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Myhash_map::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3] [d 4]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)