---
title: deque::generic_iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::generic_iterator
dev_langs:
- C++
helpviewer_keywords:
- generic_iterator member [STL/CLR]
ms.assetid: 865d1ec3-e660-4d18-9ff7-2302a3e74d49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 526a31d9d8aafa11117a92186d5b8b15dd34d1d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110574"
---
# <a name="dequegenericiterator-stlclr"></a>deque::generic_iterator (STL/CLR)
Typ iteratora do użytku ogólnego interfejs dla kontenera.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value> generic_iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano iteratora rodzajowy, używaną z ogólnym interfejsem dla tej klasy kontenera szablonu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_deque_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/deque — >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [deque — (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)   
 [deque::generic_reverse_iterator (STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)