---
description: 'Dowiedz się więcej o programie: częściowe porządkowanie szablonów funkcji (C++)'
title: Częściowe porządkowanie szablonów funkcji (C++)
ms.date: 07/30/2019
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
ms.openlocfilehash: 701c97aa819d0294f69f2fe2a71ffb9bf0210afa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145902"
---
# <a name="partial-ordering-of-function-templates-c"></a>Częściowe porządkowanie szablonów funkcji (C++)

Dostępnych może być wiele szablonów funkcji, które odpowiadają liście argumentów wywołania funkcji. C++ definiuje częściowe ustalanie kolejności szablonów funkcji w celu określenia, którą funkcję należy wywołać. Ustalanie kolejności jest częściowe, ponieważ może istnieć wiele szablonów, które są uważane za jednakowo specjalistyczne.

Kompilator wybiera najbardziej wyspecjalizowaną funkcję szablonu dostępną z możliwych dopasowań. Na przykład jeśli szablon funkcji przyjmuje typ `T` i jest dostępny inny szablon funkcji, który `T*` jest wymagany, wersja jest określana jako `T*` bardziej wyspecjalizowana. Jest preferowana w porównaniu z `T` wersją ogólną, gdy argument jest typem wskaźnika, mimo że oba byłyby dozwolone.

Użyj następującego procesu w celu określenia, czy jeden z kandydatów szablonów funkcji jest bardziej wyspecjalizowany:

1. Rozważ dwa szablony funkcji T1 i T2.

1. Zastąp parametry w T1 hipotetycznym unikatowym typem X.

1. Mając listę parametrów dla T1, zobacz czy T2 jest prawidłowym szablonem dla tej listy parametrów. Zignoruj wszystkie niejawne konwersje.

1. Powtórz ten sam proces z odwróconymi T1 i T2.

1. Jeśli jeden szablon jest prawidłową listą argumentów szablonu dla innego szablonu, ale nie jest spełniony, ten szablon jest traktowany jako mniej wyspecjalizowany niż inny szablon. Jeśli przy użyciu poprzedniego kroku oba szablony tworzą prawidłowe argumenty dla siebie, są uważane za równie wyspecjalizowane i niejednoznaczne wyniki wywołań podczas próby ich użycia.

1. Przy użyciu tych reguł:

   1. Specjalizacja szablonu dla określonego typu jest bardziej wyspecjalizowana niż ta, która przyjmuje argument typu ogólnego.

   1. Szablon przyjmujący tylko `T*` , że jest bardziej wyspecjalizowany, tylko wtedy `T` , gdy typ hipotetyczny `X*` jest prawidłowym argumentem dla `T` argumentu szablonu, ale `X` nie jest prawidłowym argumentem `T*` argumentu szablonu.

   1. `const T` jest bardziej wyspecjalizowany niż `T` , ponieważ `const X` jest prawidłowym argumentem dla `T` argumentu szablonu, ale `X` nie jest prawidłowym argumentem `const T` argumentu szablonu.

   1. `const T*` jest bardziej wyspecjalizowany niż `T*` , ponieważ `const X*` jest prawidłowym argumentem dla `T*` argumentu szablonu, ale `X*` nie jest prawidłowym argumentem `const T*` argumentu szablonu.

## <a name="example"></a>Przykład

Poniższy przykład działa jak określono w standardzie:

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```

### <a name="output"></a>Dane wyjściowe

```Output
Less specialized function called
More specialized function called
Even more specialized function for const T*
```

## <a name="see-also"></a>Zobacz też

[Szablony funkcji](../cpp/function-templates.md)
