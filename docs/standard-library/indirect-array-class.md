---
description: Dowiedz się więcej na temat klasy indirect_array
title: indirect_array — Klasa
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 47c9a0e604fd9873d7705f70624e67d9b3a22a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324044"
---
# <a name="indirect_array-class"></a>indirect_array — Klasa

Wewnętrzny, pomocniczy szablon klasy, który obsługuje obiekty, które są podzestawami valarrays przez dostarczanie operacji między tablicami podzestawu zdefiniowanymi przez określenie podzestawu indeksów nadrzędnego valarray.

## <a name="syntax"></a>Składnia

## <a name="remarks"></a>Uwagi

Klasa opisuje obiekt, który przechowuje odwołanie do obiektu `va` klasy [valarray](../standard-library/valarray-class.md) **\<Type>** , wraz z obiektem `xa` klasy `valarray<size_t>` , który opisuje sekwencję elementów do wybrania z `valarray<Type>` obiektu.

Obiekt można skonstruować `indirect_array<Type>` tylko przez napisanie wyrażenia formularza `va[xa]` . Funkcje składowe klasy indirect_array następnie zachowują się jak odpowiadające im sygnatury funkcji zdefiniowane dla `valarray<Type>` , z tą różnicą, że dotyczy tylko sekwencji wybranych elementów.

Sekwencja składa się z **XA.** elementy [size](../standard-library/valarray-class.md#size) , gdzie element `I` jest indeksem **XA**[ `I` ] w `va` .

## <a name="example"></a>Przykład:

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Dane wyjściowe

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<valarray>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
