---
title: hash_multiset::lower_bound (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::lower_bound
dev_langs: C++
helpviewer_keywords: lower_bound member [STL/CLR]
ms.assetid: 891898fa-c9e8-4132-a71d-36e5141793f1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1d18a31280cd2c0d7629dfb822107cbdde39042c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultisetlowerbound-stlclr"></a>hash_multiset::lower_bound (STL/CLR)
Wyszukuje początek zakresu, który jest zgodny z określonym kluczem.  
  
## <a name="syntax"></a>Składnia  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametry  
 klawisz  
 Wartość klucza do wyszukania.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja członkowska Określa pierwszy element `X` w kontrolowanej sekwencji, który tworzy skrót do tego samego zasobnika jako `key` i ma równoważne kolejności do `key`. Jeśli żaden taki element istnieje, zwraca [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`; w przeciwnym razie zwraca iterację wyznacza `X`. Możesz użyć do zlokalizowania na początku sekwencji elementów aktualnie w kontrolowanej sekwencji, który jest zgodny z określonym kluczem.  
  
## <a name="example"></a>Przykład  
  
```  
// cliext_hash_multiset_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*lower_bound(L'a') = {0}",   
        *c1.lower_bound(L'a'));   
    System::Console::WriteLine("*lower_bound(L'b') = {0}",   
        *c1.lower_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = a  
*lower_bound(L'b') = b  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Zobacz też  
 [hash_multiset — (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::Count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)   
 [hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash_multiset::Find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)   
 [hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)