---
title: Operator! = (kolejki) (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::queue::operator!=
dev_langs:
- C++
helpviewer_keywords:
- operator!= member [STL/CLR]
ms.assetid: aa9e23e5-518e-473c-b15c-9b610bb215d6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6282acabb882ac2921835c958c2a7e138b0a6742
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="operator-queue-stlclr"></a>operator!= (queue) (STL/CLR)
Kolejka jest równa porównania.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<typename Value,  
    typename Container>  
    bool operator!=(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 left  
 Po lewej stronie kontenera do porównania.  
  
 w prawo  
 Kontener prawo do porównania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja operatora `!(left == right)`. Można go użyć do przetestowania czy `left` nie jest taka sama jak określona `right` kiedy dwie kolejki są porównaniu elementu przez element.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_queue_operator_ne.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/kolejki >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [kolejki (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Operator == (kolejki) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)   
 [operator\< (kolejki) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)   
 [operator > = (kolejki) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [operator > (kolejki) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)   
 [operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)