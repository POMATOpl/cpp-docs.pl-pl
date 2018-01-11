---
title: set::EMPTY (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: af10279f-e9e8-4599-b59b-5b8d92b619eb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a383851532b949c2c0200b0a6fb57eda9dcc238
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="setempty-stlclr"></a>set::empty (STL/CLR)
Sprawdza, czy nie ma żadnych elementów.  
  
## <a name="syntax"></a>Składnia  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska zwraca wartość true dla pustego kontrolowanej sekwencji. Jest to równoważne [set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0`. Można użyć do sprawdzenia, czy zestaw jest pusty.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_set_empty.cpp   
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
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Ustaw (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)