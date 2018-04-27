---
title: '&lt;type_traits&gt; definicje typów | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::false_type
- xtr1common/std::false_type
- type_traits/std::true_type
- xtr1common/std::true_type
dev_langs:
- C++
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
caps.latest.revision: 13
manager: ghogen
ms.openlocfilehash: 01c4f90814cf2e4c10fa1b4177b582814dbb37d9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="lttypetraitsgt-typedefs"></a>&lt;type_traits&gt; definicje typów

|||
|-|-|
|[false_type](#false_type)|[true_type](#true_type)|

## <a name="false_type"></a>  false_type — Typedef

Przechowuje stałej o wartości false.

```cpp
typedef integral_constant<bool, false> false_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem specjalizacja szablonu `integral_constant`.

### <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="true_type"></a>  true_type — Typedef

Przechowuje stałej o wartości true.

```cpp
typedef integral_constant<bool, true> true_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem specjalizacja szablonu `integral_constant`.

### <a name="example"></a>Przykład

```cpp
// std__type_traits__true_type.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main() {
    std::cout << "false_type == " << std::boolalpha
        << std::false_type::value << std::endl;
    std::cout << "true_type == " << std::boolalpha
        << std::true_type::value << std::endl;

    return (0);
}
```

```Output
false_type == false
true_type == true
```

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>
