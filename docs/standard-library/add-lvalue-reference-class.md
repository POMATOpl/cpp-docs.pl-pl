---
title: add_lvalue_reference, klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_lvalue_reference
helpviewer_keywords:
- add_lvalue_reference
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
ms.openlocfilehash: 8dbb4f91da8d7a0bf0a90b3edc4fce2918d52a9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411204"
---
# <a name="addlvaluereference-class"></a>add_lvalue_reference, klasa

Sprawia, że odwołanie do typu z typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct add_lvalue_reference;

template <class T>
using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie modyfikatora typu przechowuje zmodyfikowany typ, który jest *T* Jeśli *T* jest odwołanie lvalue, w przeciwnym razie `T&`.

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

using namespace std;
int main()
{
    int val = 0;
    add_lvalue_reference_t<int> p = (int&)val;
    p = p;  // to quiet "unused" warning
    cout << "add_lvalue_reference_t<int> == "
        << typeid(p).name() << endl;

    return (0);
}
```

```Output
add_lvalue_reference_t<int> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<type_traits >

**Namespace:** standardowe

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_reference, klasa](../standard-library/remove-reference-class.md)<br/>
