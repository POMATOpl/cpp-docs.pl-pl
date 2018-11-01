---
title: 'Wektor&lt;bool&gt;:: reference::flip'
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: 0d212aef70228454917b2a5df9cd5165df9be35b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543779"
---
# <a name="vectorltboolgtreferenceflip"></a>Wektor&lt;bool&gt;:: reference::flip

Odwraca wartość logiczną odnośnego [wektor\<bool >](../standard-library/vector-bool-class.md) elementu.

## <a name="syntax"></a>Składnia

```cpp
void flip();
```

## <a name="example"></a>Przykład

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}

```

## <a name="output"></a>Dane wyjściowe

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<wektor >

**Namespace:** standardowe

## <a name="see-also"></a>Zobacz także

[Wektor\<bool >:: reference — klasa](../standard-library/vector-bool-reference-class.md)<br/>
[Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)<br/>
