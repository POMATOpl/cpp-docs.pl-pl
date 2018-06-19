---
title: 'Wektor&lt;bool&gt;:: reference::flip | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector/std::vector<bool>::reference::flip
dev_langs:
- C++
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97695b31d79814ec8cf08396295b02b1b7bbd1d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854304"
---
# <a name="vectorltboolgtreferenceflip"></a>Wektor&lt;bool&gt;:: reference::flip

Odwraca wartość logiczną odwoływany [wektor\<bool >](../standard-library/vector-bool-class.md) elementu.

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

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[Wektor\<bool >:: klasę referencyjną](../standard-library/vector-bool-reference-class.md)<br/>
[Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)<br/>
