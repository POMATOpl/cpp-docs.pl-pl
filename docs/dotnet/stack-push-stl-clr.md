---
title: Stack::push (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::push
dev_langs:
- C++
helpviewer_keywords:
- push member [STL/CLR]
ms.assetid: 60e5b076-c80f-4af0-a018-62cda7e081db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6236989d1bdcc9ee7f6705257c91e5509ae38878
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="stackpush-stlclr"></a>stack::push (STL/CLR)
Dodaje nowy element ostatni.  
  
## <a name="syntax"></a>Składnia  
  
```  
void push(value_type val);  
```  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska wstawia element z wartością `val` na końcu kontrolowanej sekwencji. Umożliwia ona dołączyć inny element na stosie.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_stack_push.cpp   
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
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [stos (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::pop (STL/CLR)](../dotnet/stack-pop-stl-clr.md)