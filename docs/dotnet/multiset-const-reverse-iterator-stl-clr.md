---
title: multiset::const_reverse_iterator (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::const_reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_reverse_iterator member [STL/CLR]
ms.assetid: f345ddd5-c871-4a6c-a6a4-b90eb843665c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 66899dc94efa0e27da03c12d2b130747c30f47cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="multisetconstreverseiterator-stlclr"></a>multiset::const_reverse_iterator (STL/CLR)
Typ stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>Uwagi  
 Typ zawiera opis obiektu nieokreślonego typu `T4` który może służyć jako stałej iteratora wstecznego w kontrolowanej sekwencji.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_multiset_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [Zestaw wielokrotny (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::reverse_iterator (STL/CLR)](../dotnet/multiset-reverse-iterator-stl-clr.md)