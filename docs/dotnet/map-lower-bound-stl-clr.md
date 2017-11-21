---
title: map::lower_bound (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::lower_bound
dev_langs: C++
helpviewer_keywords: lower_bound member [STL/CLR]
ms.assetid: 959651a0-f949-4cc1-859b-248b6930f16c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5cd5c26d2e2dfc206c04f26e219df7dd91609e29
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="maplowerbound-stlclr"></a>map::lower_bound (STL/CLR)
Wyszukuje początek zakresu, który jest zgodny z określonym kluczem.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska Określa pierwszy element `X` w kontrolowanej sekwencji zawierającej równoważne kolejności do `key`. Jeśli żaden taki element istnieje, zwraca [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`; w przeciwnym razie zwraca iterację wyznacza `X`. Możesz użyć do zlokalizowania na początku sekwencji elementów aktualnie w kontrolowanej sekwencji, który jest zgodny z określonym kluczem.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_map_lower_bound.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Mymap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = [a 1]  
*lower_bound(L'b') = [b 2]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [mapy (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::Count (STL/CLR)](../dotnet/map-count-stl-clr.md)   
 [map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)   
 [map::Find (STL/CLR)](../dotnet/map-find-stl-clr.md)   
 [map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)