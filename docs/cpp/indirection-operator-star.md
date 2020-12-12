---
description: 'Dowiedz się więcej o: operator pośredni: *'
title: 'Operator bezpośredni: *'
ms.date: 11/04/2016
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
ms.openlocfilehash: d82e65676178fcfc9a62b10a780360c0c69d0d2b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113912"
---
# <a name="indirection-operator-"></a>Operator bezpośredni: *

## <a name="syntax"></a>Składnia

```
* cast-expression
```

## <a name="remarks"></a>Uwagi

Operator jednoargumentowy ( <strong>\*</strong> ) odwołuje się do wskaźnika; oznacza to, że konwertuje wartość wskaźnika na wartość l. Argument operacji operatora pośredni musi być wskaźnikiem do typu. Wynik wyrażenia pośredniego jest typem, z którego pochodzi typ wskaźnika. Użycie <strong>\*</strong> operatora w tym kontekście różni się od jego znaczenia jako operatora binarnego, który jest wynikiem mnożenia.

Jeśli operand wskazuje funkcję, wynik jest oznaczeniem funkcji. Jeśli wskazuje on lokalizację magazynu, wynikiem jest l-wartość opisująca lokalizację magazynu.

Operator pośredni może być używany łącznie, aby wyłuskać wskaźniki do wskaźników. Na przykład:

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

Jeśli wartość wskaźnika jest nieprawidłowa, wynik jest niezdefiniowany. Następująca lista zawiera niektóre z najbardziej typowych warunków, które unieważniają wartość wskaźnika.

- Wskaźnik jest pustym wskaźnikiem.

- Wskaźnik określa adres lokalnego elementu, który nie jest widoczny w momencie odwołania.

- Wskaźnik określa adres, który jest nieodpowiednio wyrównany dla typu wskazywanego obiektu.

- Wskaźnik określa adres nieużywany przez program wykonujący.

## <a name="see-also"></a>Zobacz też

[Wyrażenia z operatorami jednoargumentowymi](../cpp/expressions-with-unary-operators.md)<br/>
[Wbudowane operatory, pierwszeństwo i kojarzenie języka C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Operator Address-of: &](../cpp/address-of-operator-amp.md)<br/>
[Operatory pośrednie i Address-of](../c-language/indirection-and-address-of-operators.md)
