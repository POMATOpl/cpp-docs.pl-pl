---
title: multimap::upper_bound (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multimap::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: bfb8cf64-cecf-4685-8ac9-e7228ecee809
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: adcfb64d4bea21e2adf0dab781664e8c05104cbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="multimapupperbound-stlclr"></a>multimap::upper_bound (STL/CLR)
Wyszukuje koniec zakresu, który jest zgodny z określonym kluczem.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska Określa ostatni element `X` w kontrolowanej sekwencji zawierającej równoważne kolejności do `key`. Jeśli nie zawiera żadnego takiego elementu lub `X` jest ostatniego elementu w kontrolowanej sekwencji zwraca [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`; w przeciwnym razie zwraca określający pierwszy element poza iteratora`X`. Umożliwia ona obecnie Znajdź koniec sekwencję elementów w kontrolowanej sekwencji, który jest zgodny z określonym kluczem.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_multimap_upper_bound.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    Mymultimap::iterator it = c1.upper_bound(L'a');   
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
 **Nagłówek:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::Count (STL/CLR)](../dotnet/multimap-count-stl-clr.md)   
 [multimap::equal_range (STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)   
 [multimap::Find (STL/CLR)](../dotnet/multimap-find-stl-clr.md)   
 [multimap::lower_bound (STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md)