---
title: set::rend (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: 4a98d138-ad89-4dee-b757-e798da2e0c0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0d9feda1233a6111bee1b54d02547f27c52fcf4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163767"
---
# <a name="setrend-stlclr"></a>set::rend (STL/CLR)
Określa koniec odwróconej kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca odwrotnej iteratora tego punktów poza początku kontrolowanej sekwencji. W związku z tym wyznacza `end` odwrotnej kolejności. Służy do uzyskania iterację wyznacza `current` koniec kontrolowanej sekwencji występuje w odwrotnej kolejności, ale jej stan można zmieniać w przypadku zmiany długości kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_set_rend.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Ustaw (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::BEGIN (STL/CLR)](../dotnet/set-begin-stl-clr.md)   
 [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)   
 [set::rbegin (STL/CLR)](../dotnet/set-rbegin-stl-clr.md)