---
title: 'Operator address-of: &amp;'
description: Operator address-of w języku C++.
ms.date: 10/02/2020
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 8ef7ad065281e4de58ddbdebea25950f8eb9dd06
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765286"
---
# <a name="address-of-operator-amp"></a>Operator address-of: &amp;

## <a name="syntax"></a>Składnia

> **`&`** *`cast-expression`*

## <a name="remarks"></a>Uwagi

Jednoargumentowy adres operatora ( **`&`** ) przyjmuje adres operandu. Argument operacji operatora address-of może być oznaczeniem funkcji lub l-wartością, która określa obiekt, który nie jest polem bitowym.

Operator address-of może być stosowany tylko do zmiennych typu podstawowego, struktury, klasy lub Unii, które są zadeklarowane na poziomie pliku lub do tablic indeksów. W tych wyrażeniach wyrażenie stałe, które nie zawiera operatora address-of, może być dodawane lub odejmowane od wyrażenia adresu.

W przypadku zastosowania do funkcji lub wartości l, wynik wyrażenia jest typem wskaźnika (r-Value) pochodnym typu operandu. Na przykład, jeśli operand jest typu **`char`** , wynik wyrażenia jest typu wskaźnika do **`char`** . Operator address-of, stosowany do **`const`** lub **`volatile`** obiektów, oblicza do `const type *` lub `volatile type *` , gdzie `type` jest typem oryginalnego obiektu.

Adres przeciążonej funkcji można wykonać tylko wtedy, gdy jest jasne, która wersja funkcji jest przywoływana. Zobacz [przeciążanie funkcji](function-overloading.md) , aby uzyskać informacje na temat sposobu uzyskiwania adresu określonej przeciążonej funkcji.

Gdy operator address-of jest stosowany do kwalifikowanej nazwy, wynik zależy od tego, czy *kwalifikowana nazwa* określa statyczną składową. Jeśli tak, wynik jest wskaźnikiem do typu określonego w deklaracji elementu członkowskiego. W przypadku elementu członkowskiego, który nie jest statyczny, wynik jest wskaźnikiem do *nazwy* elementu członkowskiego klasy wskazanej przez *kwalifikowana nazwa klasy*. Aby uzyskać więcej informacji na temat *nazwy klasy kwalifikowanej*, zobacz [wyrażenia podstawowe](../cpp/primary-expressions.md).

## <a name="example-address-of-static-member"></a>Przykład: adres statycznego elementu członkowskiego

Poniższy fragment kodu przedstawia sposób, w jaki wynik operatora address-of różni się w zależności od tego, czy element członkowski klasy jest statyczny:

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

W tym przykładzie wyrażenie `&PTM::fValue` zwraca typ `float *` zamiast typu, `float PTM::*` ponieważ `fValue` jest statycznym elementem członkowskim.

## <a name="example-address-of-a-reference-type"></a>Przykład: adres typu odwołania

Zastosowanie operatora address-of do typu referencyjnego daje ten sam wynik, co zastosowanie operatora do obiektu, do którego jest powiązane odwołanie. Przykład:

```cpp
// expre_Address_Of_Operator2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   double d;        // Define an object of type double.
   double& rd = d;  // Define a reference to the object.

   // Obtain and compare their addresses
   if( &d == &rd )
      cout << "&d equals &rd" << endl;
}
```

```Output
&d equals &rd
```

## <a name="example-function-address-as-parameter"></a>Przykład: adres funkcji jako parametr

Poniższy przykład używa operatora address-of do przekazania argumentu wskaźnika do funkcji:

```cpp
// expre_Address_Of_Operator3.cpp
// compile with: /EHsc
// Demonstrate address-of operator &

#include <iostream>
using namespace std;

// Function argument is pointer to type int
int square( int *n ) {
   return (*n) * (*n);
}

int main() {
   int mynum = 5;
   cout << square( &mynum ) << endl;   // pass address of int
}
```

```Output
25
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia z operatorami jednoargumentowymi](../cpp/expressions-with-unary-operators.md)<br/>
[Wbudowane operatory, pierwszeństwo i łączność języka C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Deklarator odwołania do wartości L: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Operatory pośrednie i Address-of](../c-language/indirection-and-address-of-operators.md)
