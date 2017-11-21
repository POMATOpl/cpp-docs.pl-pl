---
title: Pair::Second (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::second
dev_langs: C++
helpviewer_keywords: second member [STL/CLR]
ms.assetid: f30d3d1f-c7be-45d2-92ff-6861b96a92ff
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f0393664bd49f4e961e9348b4e957f0e95038ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="pairsecond-stlclr"></a>pair::second (STL/CLR)
Drugi opakowane wartości.  
  
## <a name="syntax"></a>Składnia  
  
```  
Value2 second;  
```  
  
## <a name="remarks"></a>Uwagi  
 Obiekt przechowuje drugi zakodowana wartość.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_pair_second.cpp   
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
 [Pair::First (STL/CLR)](../dotnet/pair-first-stl-clr.md)   
 [Pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)   
 [Pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)