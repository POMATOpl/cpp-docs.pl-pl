---
description: Dowiedz się więcej na temat instrukcji Return (C++)
title: return — instrukcja (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: bb847900a0a9fc4c5d723d1b0392f27b6b5cf667
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340479"
---
# <a name="return-statement-c"></a>return — instrukcja (C++)

Kończy wykonywanie funkcji i zwraca kontrolę do funkcji wywołującej (lub systemu operacyjnego, Jeśli przeniesiesz kontrolę z `main` funkcji). Wykonanie wznowione w funkcji wywołującej w punkcie bezpośrednio po wywołaniu.

## <a name="syntax"></a>Składnia

```
return [expression];
```

## <a name="remarks"></a>Uwagi

`expression`Klauzula, jeśli jest obecna, jest konwertowana na typ określony w deklaracji funkcji, tak jak w przypadku wykonywania inicjalizacji. Konwersja z typu wyrażenia na **`return`** Typ funkcji może tworzyć obiekty tymczasowe. Aby uzyskać więcej informacji o tym, jak i kiedy obiekty tymczasowe są tworzone, zobacz [obiekty tymczasowe](../cpp/temporary-objects.md).

Wartość `expression` klauzuli jest zwracana do funkcji wywołującej. Jeśli wyrażenie zostanie pominięte, zwracana wartość funkcji jest niezdefiniowana. Konstruktory i destruktory oraz funkcje typu **`void`** nie mogą określać wyrażenia w **`return`** instrukcji. Funkcje wszystkich innych typów muszą określać wyrażenie w **`return`** instrukcji.

Gdy przepływ sterowania opuszcza blok zawierający definicję funkcji, wynik jest taki sam, jak gdyby **`return`** instrukcja bez wyrażenia została wykonana. Jest to nieprawidłowe dla funkcji, które są zadeklarowane jako zwracające wartość.

Funkcja może zawierać dowolną liczbę **`return`** instrukcji.

Poniższy przykład używa wyrażenia z **`return`** instrukcją, aby uzyskać największą z dwóch liczb całkowitych.

## <a name="example"></a>Przykład

```cpp
// return_statement2.cpp
#include <stdio.h>

int max ( int a, int b )
{
   return ( a > b ? a : b );
}

int main()
{
    int nOne = 5;
    int nTwo = 7;

    printf_s("\n%d is bigger\n", max( nOne, nTwo ));
}
```

## <a name="see-also"></a>Zobacz także

[Instrukcje skoku](../cpp/jump-statements-cpp.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
