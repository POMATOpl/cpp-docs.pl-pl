---
title: "is_pod — klasa | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_pod
dev_langs: C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67341c89d480f6ef0d44415f65dd0cd37bb065fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="ispod-class"></a>is_pod — Klasa
Testy, jeśli typ jest POD.  
  
## <a name="syntax"></a>Składnia  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Parametry  
*T*  
Typ do zapytania.  
  
## <a name="remarks"></a>Uwagi  
`is_pod<T>::value`jest `true` Jeśli typ *T* jest zwykły stare dane (POD). W przeciwnym razie jest `false`.  
  
Typów arytmetycznych, Typy wyliczeniowe typów wskaźnikowych i wskaźnika do elementu członkowskiego typy są POD.  
  
Kwalifikowana cv wersji typ POD jest typ POD.  
  
Tablica POD jest POD.  
  
Struktura lub związek, w których elementy członkowskie danych niestatyczna są POD, jest POD jeśli ma ona:  
  
-   Nie konstruktorów zadeklarowanych przez użytkownika.  
  
-   Nie członków prywatnych lub chronionych danych niestatycznego.  
  
-   Nie mają klas podstawowych.  
  
-   Nie funkcji wirtualnych.  
  
-   Nie niestatyczna elementy członkowskie danych typu referencyjnego.  
  
-   Nie operatora przypisania kopii zdefiniowane przez użytkownika.  
  
-   Nie ma destruktora zdefiniowane przez użytkownika.  
  
W związku z tym można rekursywnie kompilacji POD struktury i tablic zawierających POD struktury i tablic.  
  
## <a name="example"></a>Przykład  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Wymagania  
**Nagłówek:** \<type_traits >  
  
**Namespace:** Standard  
  
## <a name="see-also"></a>Zobacz też  
[< type_traits >](../standard-library/type-traits.md)



