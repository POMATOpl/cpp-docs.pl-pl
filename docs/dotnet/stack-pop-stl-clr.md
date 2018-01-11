---
title: Stack::POP (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::pop
dev_langs: C++
helpviewer_keywords: pop member [STL/CLR]
ms.assetid: b7565385-9e6b-432d-8c71-c62c9c6ad90d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 059e65ff61f478a854364c7c128573f2b3486bd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="stackpop-stlclr"></a>stack::pop (STL/CLR)
Usuwa ostatnim elemencie.  
  
## <a name="syntax"></a>Składnia  
  
```  
void pop();  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska usuwa ostatniego elementu w kontrolowanej sekwencji musi być niepusta. Umożliwia ona skrócić czas stosu przez jeden element z tyłu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_stack_pop.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [stos (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)