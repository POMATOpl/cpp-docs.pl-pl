---
title: collection_adapter::mapped_type (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::mapped_type
dev_langs:
- C++
helpviewer_keywords:
- mapped_type member [STL/CLR]
ms.assetid: eece6a47-611a-47d4-8dfc-cfbbc4aeb67b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58c13f0ee64ddea0bd044224ba393584a48ee998
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="collectionadaptermappedtype-stlclr"></a>collection_adapter::mapped_type (STL/CLR)
Typ wartości słownika.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef Value mapped_type;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ jest synonimem parametru szablonu `Value`, w specjalizacji dla `IDictionary` lub `IDictionary<Value>`; w przeciwnym razie nie jest zdefiniowany.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_collection_adapter_mapped_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/karty >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [collection_adapter — (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::key_type (STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)