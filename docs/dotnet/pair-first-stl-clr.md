---
title: Pair::First (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::first
dev_langs:
- C++
helpviewer_keywords:
- first member [STL/CLR]
ms.assetid: 0dd2278f-adf9-46df-8ac8-7e8e1a2ef52e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2ad04aa9887fe928abdeeaaa98d21da8f9c45772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131494"
---
# <a name="pairfirst-stlclr"></a>pair::first (STL/CLR)
Pierwszy zakodowana wartość.  
  
## <a name="syntax"></a>Składnia  
  
```  
Value1 first;  
```  
  
## <a name="remarks"></a>Uwagi  
 Obiekt przechowuje pierwszy zakodowana wartość.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/Narzędzia >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [para (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [Pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)   
 [Pair::Second (STL/CLR)](../dotnet/pair-second-stl-clr.md)   
 [pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)