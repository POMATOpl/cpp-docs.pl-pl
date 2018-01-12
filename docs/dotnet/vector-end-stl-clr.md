---
title: Vector::end (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::end
dev_langs: C++
helpviewer_keywords: end member [STL/CLR]
ms.assetid: 21fcaf1b-7f14-4dc4-a312-fa30e631ea0d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 55d4aac9d4607361ff896d8b2e24109719bf68d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="vectorend-stlclr"></a>vector::end (STL/CLR)
Określa koniec kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca iteratora dostępie swobodnym tego punkty bezpośrednio po zakończeniu kontrolowanej sekwencji. Służy do uzyskania iterację wyznacza `current` koniec kontrolowanej sekwencji, ale jej stan można zmieniać w przypadku zmiany długości kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_vector_end.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/wektor >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Wektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)   
 [Vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)   
 [vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)