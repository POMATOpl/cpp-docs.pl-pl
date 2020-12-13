---
description: Dowiedz się więcej na temat klasy mask_array
title: mask_array — Klasa
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: d3eb105c7779ff54ddbec3d68a518dc74d089903
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149360"
---
# <a name="mask_array-class"></a>mask_array — Klasa

Wewnętrzny, pomocniczy szablon klasy, który obsługuje obiekty, które są podzbiorami elementu nadrzędnego valarrays, określone za pomocą wyrażenia logicznego, dostarczając operacje między tablicami podzbioru.

## <a name="syntax"></a>Składnia

## <a name="remarks"></a>Uwagi

Klasa opisuje obiekt, który przechowuje odwołanie do obiektu `va` klasy [valarray](../standard-library/valarray-class.md) **\<Type>** , wraz z obiektem `ba` klasy [valarray \<bool>](../standard-library/valarray-bool-class.md), który opisuje sekwencję elementów do wybrania z `valarray<Type>` obiektu.

Obiekt można skonstruować `mask_array<Type>` tylko przez napisanie wyrażenia w postaci [VA&#91;ba&#93;](../standard-library/valarray-class.md#op_at). Funkcje składowe klasy mask_array następnie zachowują się jak odpowiadające im sygnatury funkcji zdefiniowane dla `valarray<Type>` , z tą różnicą, że dotyczy tylko sekwencji wybranych elementów.

Sekwencja składa się z najwyżej `ba.size` elementów. Element *J* jest uwzględniany tylko wtedy, gdy **ba**[ *J*] ma wartość true. W związku z tym istnieje wiele elementów w sekwencji, ponieważ w programie istnieją prawdziwe elementy `ba` . Jeśli `I` jest indeksem najniższej wartości true w `ba` , wówczas wartość **VA**[ `I` ] jest elementem zero w wybranej sekwencji.

## <a name="example"></a>Przykład

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Dane wyjściowe

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<valarray>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
