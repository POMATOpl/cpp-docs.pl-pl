---
title: set::size_type (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::size_type
dev_langs: C++
helpviewer_keywords: size_type member [STL/CLR]
ms.assetid: df478b73-b2e6-4add-b22a-39a216753037
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 432f147c7eded15909fd503b82891f52948072b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="setsizetype-stlclr"></a>set::size_type (STL/CLR)
Typ podpisem odległość między dwoma elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef int size_type;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano liczbą nieujemną elementu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_set_size_type.cpp   
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
  
// compute positive difference   
    Myset::size_type diff = 0;   
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Ustaw (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::EMPTY (STL/CLR)](../dotnet/set-empty-stl-clr.md)