---
description: 'Dowiedz się więcej na temat: const_cast — operator'
title: Operator const_cast
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: c0c08402450773368914facb719c4ddf97b7503d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344669"
---
# <a name="const_cast-operator"></a>Operator const_cast

Usuwa **`const`** atrybuty, **`volatile`** i **`__unaligned`** z klasy.

## <a name="syntax"></a>Składnia

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Uwagi

Wskaźnik do dowolnego typu obiektu lub wskaźnika do składowej danych może być jawnie konwertowany na typ, który jest identyczny z wyjątkiem **`const`** **`volatile`** **`__unaligned`** kwalifikatorów, i. W przypadku wskaźników i odwołań wynik będzie odnosił się do oryginalnego obiektu. W przypadku wskaźników do elementów członkowskich danych wynik będzie odwoływać się do tego samego elementu członkowskiego, co oryginalny wskaźnik (uncast) do elementu członkowskiego danych. W zależności od typu obiektu, do którego istnieje odwołanie, operacja zapisu za pomocą wskaźnika, odwołania lub wskaźnika do składowej danych może spowodować niezdefiniowane zachowanie.

Operatora nie można użyć **`const_cast`** do bezpośredniego przesłania stałego stanu zmiennej stałej.

**`const_cast`** Operator konwertuje wartość wskaźnika o wartości null na wartość wskaźnika o wartości null typu docelowego.

## <a name="example"></a>Przykład

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

W wierszu zawierającym **`const_cast`** Typ danych **`this`** wskaźnika to `const CCTest *` . **`const_cast`** Operator zmienia typ danych **`this`** wskaźnika na `CCTest *` , umożliwiając modyfikowanie elementu członkowskiego `number` . Rzutowanie jest przeznaczone tylko dla pozostałej części instrukcji, w której występuje.

## <a name="see-also"></a>Zobacz też

[Operatory rzutowania](../cpp/casting-operators.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
