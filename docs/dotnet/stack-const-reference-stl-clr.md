---
title: Stack::const_reference (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: 36be8e21-f2b8-4c2e-a00e-276e73f0d802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 828d0a365a9653e0d7fe35730ef17f6ef233bd10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="stackconstreference-stlclr"></a>stack::const_reference (STL/CLR)
Typ stałego odwołania do elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano stałej odwołanie do elementu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_stack_const_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mystack::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [stos (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Stack::Reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)   
 [stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)