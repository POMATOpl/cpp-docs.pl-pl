---
title: deque::difference_type (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::difference_type
dev_langs:
- C++
helpviewer_keywords:
- difference_type member [STL/CLR]
ms.assetid: deb00a44-80c7-42f8-ad17-1d36377dec88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: df1c7f7f435d1a80a9fafba04c85a37d698f3f51
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="dequedifferencetype-stlclr"></a>deque::difference_type (STL/CLR)
Typy podpisane odległość między dwoma elementami.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef int difference_type;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ w tym artykule opisano liczba podpisanego elementu.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_deque_difference_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::difference_type diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/deque — >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [deque — (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::size_type (STL/CLR)](../dotnet/deque-size-type-stl-clr.md)