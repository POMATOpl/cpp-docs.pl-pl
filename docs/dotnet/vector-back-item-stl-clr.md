---
title: Vector::back_item (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::back_item
dev_langs:
- C++
helpviewer_keywords:
- back_item member [STL/CLR]
ms.assetid: 9658ffa8-7bde-4242-9ed9-ca42be0d1433
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8a69eae367e809d6493a0d5aa975ce25bdf2dac5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166845"
---
# <a name="vectorbackitem-stlclr"></a>vector::back_item (STL/CLR)
Uzyskuje dostęp do ostatniego elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
property value_type back_item;  
```  
  
## <a name="remarks"></a>Uwagi  
 Właściwość uzyskuje dostęp do ostatniego elementu w kontrolowanej sekwencji musi być niepusta. Możesz użyć do odczytu lub zapisu ostatniego elementu, gdy wiesz, że istnieje.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_vector_back_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/wektor >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Wektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)   
 [Vector::Front (STL/CLR)](../dotnet/vector-front-stl-clr.md)   
 [vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)