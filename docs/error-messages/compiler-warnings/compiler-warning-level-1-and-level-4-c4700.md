---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1 i poziom 4) C4700'
title: Ostrzeżenie C4700 kompilatora (poziom 1 i 4)
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: 7ba19bdd6d8e25e095f796adc8cdb60b5cc8d325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241602"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Ostrzeżenie C4700 kompilatora (poziom 1 i 4)

> użyto niezainicjowanej zmiennej lokalnej "*name*"

*Nazwa* zmiennej lokalnej została *użyta*, czyli odczytana z, przed przypisaniem do niej wartości. W C i C++ zmienne lokalne nie są domyślnie inicjowane. Niezainicjowane zmienne mogą zawierać dowolną wartość, a ich użycie prowadzi do niezdefiniowanego zachowania. Ostrzeżenie C4700 niemal zawsze wskazuje usterkę, która może spowodować nieprzewidywalne wyniki lub awarie w programie.

Aby rozwiązać ten problem, można inicjować zmienne lokalne, gdy są one zadeklarowane, lub przypisać do nich wartość przed użyciem. Funkcja może służyć do inicjowania zmiennej, która jest przenoszona jako parametr odwołania, lub gdy jej adres jest przenoszona jako parametr wskaźnika.

## <a name="example"></a>Przykład

Ten przykład generuje C4700, gdy zmienne t, u i v są używane przed zainicjowaniem, i pokazuje rodzaj wartości elementu bezużytecznego, która może wynikać. Zmienne x, y i z nie powodują ostrzeżenia, ponieważ są one inicjowane przed użyciem:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

Gdy ten kod jest uruchamiany, t, u i v nie zostanie zainicjowany, a dane wyjściowe dla s są nieprzewidywalne:

```Output
Value in s: 37816963
Value in w: 42
```
