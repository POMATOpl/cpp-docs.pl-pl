---
description: 'Dowiedz się więcej o: Operatory addytywne: + i-'
title: 'Operatory dodawania: + i -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
ms.openlocfilehash: f87a8682b6f282668c168262cd28230745cb4402
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288376"
---
# <a name="additive-operators--and--"></a>Operatory dodawania: + i -

## <a name="syntax"></a>Składnia

```
expression + expression
expression - expression
```

## <a name="remarks"></a>Uwagi

Operatory addytywne to:

- Dodawanie ( **+** )

- Odejmowanie ( **-** )

Te operatory dwuargumentowe mają łączność od lewej do prawej.

Operatory addytywne pobierają operandy arytmetyczne lub typu wskaźnika. Wynik operatora dodawania ( **+** ) jest sumą argumentów operacji. Wynikiem odejmowania ( **-** ) jest różnica między operandami. Jeśli jeden lub oba operandy są wskaźnikami, muszą być wskaźnikami do obiektów, a nie do funkcji. Jeśli oba operandy są wskaźnikami, wyniki nie są znaczące, chyba że oba są wskaźnikami do obiektów w tej samej tablicy.

Operatory addytywne pobierają operandy dla typów *arytmetycznych*, *całkowitych* i *skalarnych* . Są one zdefiniowane w poniższej tabeli.

### <a name="types-used-with-additive-operators"></a>Typy używane z operatorami dodatków

|Typ|Znaczenie|
|----------|-------------|
|*obliczeń*|Typy całkowite i zmiennoprzecinkowe są nazywane zbiorczo typami "arytmetycznymi".|
|*integraln*|Typy char i int wszystkich rozmiarów (Long, Short) i Enumeration są typami całkowitymi.|
|*Funkcja*|Argumenty operacji skalarnych to operandy typu arytmetycznego lub wskaźnika.|

Odpowiednie kombinacje dla tych operatorów są następujące:

*operacje arytmetyczne*  +  *operacje arytmetyczne*

Funkcja *skalarna*  +  *część całkowita*

*część całkowita*  +  Funkcja *skalarna*

*operacje arytmetyczne*  -  *operacje arytmetyczne*

Funkcja *skalarna*  -  Funkcja *skalarna*

Należy zauważyć, że dodawanie i odejmowanie nie są odpowiednikami operacji.

Jeśli oba operandy są typu arytmetycznego, konwersje omówione w [konwersji standardowej](standard-conversions.md) są stosowane do operandów, a wynik jest konwertowany typ.

## <a name="example"></a>Przykład

```cpp
// expre_Additive_Operators.cpp
// compile with: /EHsc
#include <iostream>
#define SIZE 5
using namespace std;
int main() {
   int i = 5, j = 10;
   int n[SIZE] = { 0, 1, 2, 3, 4 };
   cout  << "5 + 10 = " << i + j << endl
         << "5 - 10 = " << i - j << endl;

   // use pointer arithmetic on array

   cout << "n[3] = " << *( n + 3 ) << endl;
}
```

## <a name="pointer-addition"></a>Dodawanie wskaźnika

Jeśli jeden z operandów w operacji dodawania jest wskaźnikiem do tablicy obiektów, drugi musi być typu całkowitego. Wynik jest wskaźnikiem, który jest tego samego typu co oryginalny wskaźnik i wskazuje na inny element tablicy. Poniższy fragment kodu ilustruje tę koncepcję:

```cpp
short IntArray[10]; // Objects of type short occupy 2 bytes
short *pIntArray = IntArray;

for( int i = 0; i < 10; ++i )
{
    *pIntArray = i;
    cout << *pIntArray << "\n";
    pIntArray = pIntArray + 1;
}
```

Mimo że wartość całkowita 1 jest dodawana do, nie ma `pIntArray` znaczenia "Dodaj 1 do adresu"; zamiast tego oznacza "Dostosuj wskaźnik, aby wskazywał następny obiekt w tablicy", który ma wartość 2 bajtów (lub `sizeof( int )` ).

> [!NOTE]
> Kod w formularzu `pIntArray = pIntArray + 1` rzadko znajduje się w programach C++. Aby wykonać przyrost, preferowane są następujące formularze: `pIntArray++` lub `pIntArray += 1` .

## <a name="pointer-subtraction"></a>Odejmowanie wskaźnika

Jeśli oba operandy są wskaźnikami, wynikiem odejmowania jest różnica (w elementach tablicy) między operandami. Wyrażenie odejmowania daje podpisany wynik całkowity typu `ptrdiff_t` (zdefiniowany w standardowym pliku dołączanym \<stddef.h> ).

Jeden z operandów może być typu całkowitego, o ile jest to drugi operand. Wynik odejmowania jest tego samego typu co oryginalny wskaźnik. Wartość odejmowania jest wskaźnikiem do elementu tablicy (*n*  -  *i*), gdzie *n* jest elementem wskazywanym przez oryginalny wskaźnik i jest wartością całkowitą drugiego operandu. 

## <a name="see-also"></a>Zobacz też

[Wyrażenia z operatorami dwuargumentowymi](../cpp/expressions-with-binary-operators.md)<br/>
[Wbudowane operatory, pierwszeństwo i kojarzenie języka C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Operatory addytywne języka C](../c-language/c-additive-operators.md)
