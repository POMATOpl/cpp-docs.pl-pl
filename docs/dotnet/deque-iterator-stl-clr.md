---
title: deque::iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::iterator
dev_langs: C++
helpviewer_keywords: iterator member [STL/CLR]
ms.assetid: 3529e793-5d56-4cb2-898d-fdedb90b5c0c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 263862aa76e8e913de7650b10bbfc6dc2914ed0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="dequeiterator-stlclr"></a>deque::iterator (STL/CLR)
Typ iteratora dla kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ zawiera opis obiektu nieokreślonego typu `T1` który może służyć jako iterator dostępie swobodnym w kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_deque_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/deque — >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [deque — (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)