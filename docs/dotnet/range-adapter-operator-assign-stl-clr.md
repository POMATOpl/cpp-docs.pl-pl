---
title: range_adapter::operator = (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::operator=
- cliext::range_adapter::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: ac378ccc-a42c-4a90-bc27-9b416bee7fa9
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 41b3e9e197347525ca64a549871c0ae44a4ba274
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="rangeadapteroperator-stlclr"></a>range_adapter::operator= (STL/CLR)
Zastępuje pary iteratora przechowywane.  
  
## <a name="syntax"></a>Składnia  
  
```  
range_adapter<Iter>% operator=(range_adapter<Iter>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 w prawo  
 Karta do skopiowania.  
  
## <a name="remarks"></a>Uwagi  
 Element członkowski operatora kopie `right` do obiektu, zwraca `*this`. Umożliwia ona Zamień pary iteratora przechowywanych kopię pary iteratora przechowywanych w `right`.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_range_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Myrange c1(d1.begin(), d1.end());   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myrange c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/karty >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)