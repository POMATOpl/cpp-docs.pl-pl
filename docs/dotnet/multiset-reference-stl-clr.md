---
title: multiset::Reference (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::reference
dev_langs: C++
helpviewer_keywords: reference member [STL/CLR]
ms.assetid: fb2bf992-d410-4b93-b087-cf2ac4b12e87
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aca753688bd4c9f7761702581c087b567a355daa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="multisetreference-stlclr"></a>multiset::reference (STL/CLR)
Typ odwołania do elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano odwołanie do elementu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_multiset_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mymultiset::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Zestaw wielokrotny (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::const_reference (STL/CLR)](../dotnet/multiset-const-reference-stl-clr.md)   
 [multiset::value_type (STL/CLR)](../dotnet/multiset-value-type-stl-clr.md)