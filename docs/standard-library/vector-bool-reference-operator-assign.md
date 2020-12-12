---
description: 'Dowiedz się więcej o: Vector &lt; bool &gt; :: Reference:: operator ='
title: 'Vector &lt; bool &gt; :: Reference:: operator ='
ms.date: 11/04/2016
f1_keywords:
- =
- operator=
- vector<bool>::reference::operator=
- std::vector<bool>::reference::operator=
helpviewer_keywords:
- = operator, with specific C++ Standard Library objects
- reference::operator=
ms.assetid: eed20d81-36b9-40b2-a3b6-340ed0bb4f34
ms.openlocfilehash: eb6efe7d0e5d59d1135430a3dc8b544dcee3678f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280368"
---
# <a name="vectorltboolgtreferenceoperator"></a>Vector &lt; bool &gt; :: Reference:: operator =

Przypisuje do bitu wartość logiczną lub wartość przechowywaną przez odnośny element.

## <a name="syntax"></a>Składnia

```cpp
reference& operator=(const reference& Right);

reference& operator=(bool Val);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Odwołanie elementu, którego wartość ma być przypisana do bitu.

*Użyte*\
Wartość logiczna, który ma być przypisana do bitu.

## <a name="example"></a>Przykład

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

## <a name="output"></a>Dane wyjściowe

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<vector>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Vector \<bool> :: Reference — Klasa](../standard-library/vector-bool-reference-class.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
