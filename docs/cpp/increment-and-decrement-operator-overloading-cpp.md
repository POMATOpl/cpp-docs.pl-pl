---
description: 'Dowiedz się więcej na temat: przyrostowe i zmniejszenie przeciążania operatora (C++)'
title: Przeładowanie operatorów inkrementacji i dekrementacji (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: f2704a1c10375bf8422324d90f41c6e3ac245505
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113925"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Przeładowanie operatorów inkrementacji i dekrementacji (C++)

Operatory przyrostu i zmniejszania wchodzą w skład specjalnej kategorii, ponieważ istnieją dwie warianty każdej z nich:

- Przedrastaj i postinkrementacji

- Zmniejszenie i postdekrementacyjne

Gdy zapisujesz przeciążone funkcje operatora, może być przydatne, aby zaimplementować oddzielne wersje dla prefiksu i przyrostowych wersji tych operatorów. Aby rozróżnić te dwa, zaobserwuj następującą regułę: prefiks formy operatora jest zadeklarowany dokładnie tak samo jak każdy inny operator jednoargumentowy; formularz Przyrostkowy akceptuje dodatkowy argument typu **`int`** .

> [!NOTE]
> Podczas określania przeciążonego operatora dla przyrostowej formy operatora zwiększania lub zmniejszania, dodatkowy argument musi być typu **`int`** ; określenie dowolnego innego typu generuje błąd.

Poniższy przykład pokazuje, jak definiować operatory prefiksu i zwiększania przyrostu i zmniejszania dla `Point` klasy:

```cpp
// increment_and_decrement1.cpp
class Point
{
public:
   // Declare prefix and postfix increment operators.
   Point& operator++();       // Prefix increment operator.
   Point operator++(int);     // Postfix increment operator.

   // Declare prefix and postfix decrement operators.
   Point& operator--();       // Prefix decrement operator.
   Point operator--(int);     // Postfix decrement operator.

   // Define default constructor.
   Point() { _x = _y = 0; }

   // Define accessor functions.
   int x() { return _x; }
   int y() { return _y; }
private:
   int _x, _y;
};

// Define prefix increment operator.
Point& Point::operator++()
{
   _x++;
   _y++;
   return *this;
}

// Define postfix increment operator.
Point Point::operator++(int)
{
   Point temp = *this;
   ++*this;
   return temp;
}

// Define prefix decrement operator.
Point& Point::operator--()
{
   _x--;
   _y--;
   return *this;
}

// Define postfix decrement operator.
Point Point::operator--(int)
{
   Point temp = *this;
   --*this;
   return temp;
}
int main()
{
}
```

Te same operatory można definiować w zakresie plików (globalnie) przy użyciu następujących głowic funkcji:

```cpp
friend Point& operator++( Point& )      // Prefix increment
friend Point& operator++( Point&, int ) // Postfix increment
friend Point& operator--( Point& )      // Prefix decrement
friend Point& operator--( Point&, int ) // Postfix decrement
```

Argument typu **`int`** , który oznacza przyrostkową formę operatora przyrostu lub zmniejszania nie jest często używany do przekazywania argumentów. Zwykle zawiera wartość 0. Można go jednak użyć w następujący sposób:

```cpp
// increment_and_decrement2.cpp
class Int
{
public:
    Int &operator++( int n );
private:
    int _i;
};

Int& Int::operator++( int n )
{
    if( n != 0 )    // Handle case where an argument is passed.
        _i += n;
    else
        _i++;       // Handle case where no argument is passed.
    return *this;
}
int main()
{
   Int i;
   i.operator++( 25 ); // Increment by 25.
}
```

Nie ma składni do przekazywania tych wartości innych niż jawne wywołanie, jak pokazano w powyższym kodzie. Bardziej prostym sposobem implementacji tej funkcji jest Przeciążenie operatora dodawania/przypisywania ( **+=** ).

## <a name="see-also"></a>Zobacz też

[Przeciążanie operatora](../cpp/operator-overloading.md)
