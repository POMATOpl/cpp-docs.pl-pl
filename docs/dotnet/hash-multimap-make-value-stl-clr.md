---
title: hash_multimap::make_value (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::make_value
dev_langs:
- C++
helpviewer_keywords:
- make_value member [STL/CLR]
ms.assetid: 300fb6ec-98c8-48d5-8626-0646878a8462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1e4fbbc91ba3bff116bd1f2c7307d60f95877d3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109638"
---
# <a name="hashmultimapmakevalue-stlclr"></a>hash_multimap::make_value (STL/CLR)
Tworzy obiekt wartość.  
  
## <a name="syntax"></a>Składnia  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do użycia.  
  
 zamapowane  
 Zmapowane wartość do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca `value_type` obiektu, którego klucz jest `key` , którego wartość zamapowanego jest `mapped`. Można go użyć do zredagowania odpowiednie do użycia z wielu innych funkcji elementów członkowskich obiektu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multimap_make_value.cpp   
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
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multimap — (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::key_type (STL/CLR)](../dotnet/hash-multimap-key-type-stl-clr.md)   
 [hash_multimap::mapped_type (STL/CLR)](../dotnet/hash-multimap-mapped-type-stl-clr.md)   
 [hash_multimap::value_type (STL/CLR)](../dotnet/hash-multimap-value-type-stl-clr.md)