---
description: 'Dowiedz się więcej na temat: &lt; type_traits &gt; Typedefs'
title: '&lt;type_traits &gt; Typedefs'
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::false_type
- xtr1common/std::false_type
- type_traits/std::true_type
- xtr1common/std::true_type
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
ms.openlocfilehash: ec5902ce21b3ca26e44acb66cc738a12b6478010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253302"
---
# <a name="lttype_traitsgt-typedefs"></a>&lt;type_traits &gt; Typedefs

[false_type](#false_type)\
[true_type](#true_type)

## <a name="false_type-typedef"></a><a name="false_type"></a> false_type typedef

Przechowuje stałą całkowitą z wartością false.

```cpp
typedef integral_constant<bool, false> false_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla specjalizacji szablonu `integral_constant` .

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

## <a name="true_type-typedef"></a><a name="true_type"></a> true_type typedef

Zawiera stałą całkowitą o wartości true.

```cpp
typedef integral_constant<bool, true> true_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla specjalizacji szablonu `integral_constant` .

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

[<type_traits>](../standard-library/type-traits.md)
