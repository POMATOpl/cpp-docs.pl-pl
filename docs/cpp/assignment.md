---
description: 'Dowiedz się więcej o: przypisywaniu'
title: Przypisanie
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: 696706202e70e8baf50dda34ac98ff9bca5dcda2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319495"
---
# <a name="assignment"></a>Przypisanie

Operator przypisania ( **=** ) to, dokładnie mówiąc, operator binarny. Jego deklaracja jest taka sama jak każdy inny operator binarny z następującymi wyjątkami:

- Musi to być niestatyczna funkcja członkowska. Nie można zadeklarować **operatora =** jako funkcji nienależącej do elementu członkowskiego.
- Nie są dziedziczone przez klasy pochodne.
- Funkcja **operatora domyślnego =** może być generowana przez kompilator dla typów klas, jeśli nie istnieje.

Poniższy przykład ilustruje sposób deklarowania operatora przypisania:

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

Dostarczony argument jest prawą stroną wyrażenia. Operator zwraca obiekt, aby zachować zachowanie operatora przypisania, który zwraca wartość po lewej stronie po zakończeniu przypisywania. Pozwala to na łączenie łańcuchów przypisań, takich jak:

```cpp
pt1 = pt2 = pt3;
```

Nie należy mylić operatora przypisania kopii z konstruktorem kopiującym. Ten drugi jest wywoływany podczas tworzenia nowego obiektu z istniejącej:

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> Zaleca się przestrzeganie [reguły trzech](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) , że Klasa, która definiuje operator przypisania kopii, powinna również jawnie definiować Konstruktor kopiujący, destruktor i, rozpoczynając od c++ 11, przenieść konstruktora i operator przypisania przenoszenia.

## <a name="see-also"></a>Zobacz też

- [Przeciążanie operatora](../cpp/operator-overloading.md)
- [Konstruktory kopiujące i kopiujące operatory przypisania (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)
