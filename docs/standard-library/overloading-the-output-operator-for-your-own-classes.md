---
description: 'Dowiedz się więcej na temat: przeciążanie &lt; &lt; operatora dla własnych klas'
title: Przeciążanie &lt; &lt; operatora dla własnych klas
ms.date: 11/04/2016
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
ms.openlocfilehash: 206d6ccb50c7cb3706c66adeb6c1429a04775fc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340843"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Przeciążanie &lt; &lt; operatora dla własnych klas

Strumienie wyjściowe używają operatora wstawiania ( `<<` ) dla typów standardowych. Można również przeciążyć `<<` operatora dla własnych klas.

## <a name="example"></a>Przykład

W `write` przykładzie funkcji pokazano użycie `Date` struktury. Data jest idealnym kandydatem dla klasy języka C++, w której elementy członkowskie danych (miesiąc, dzień i rok) są ukryte przed wyświetleniem. Strumień wyjściowy jest logicznym miejscem docelowym do wyświetlania takiej struktury. Ten kod wyświetla datę przy użyciu `cout` obiektu:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Aby `cout` zaakceptować `Date` obiekt po operatorze wstawiania, przeciążać operator wstawiania, aby rozpoznać obiekt po `ostream` lewej stronie i `Date` po prawej stronie. Funkcja przeciążonego `<<` operatora musi być zadeklarowana jako zaprzyjaźniona Klasa `Date` , aby można było uzyskać dostęp do danych prywatnych w `Date` obiekcie.

```cpp
// overload_date.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Date
{
    int mo, da, yr;
public:
    Date(int m, int d, int y)
    {
        mo = m; da = d; yr = y;
    }
    friend ostream& operator<<(ostream& os, const Date& dt);
};

ostream& operator<<(ostream& os, const Date& dt)
{
    os << dt.mo << '/' << dt.da << '/' << dt.yr;
    return os;
}

int main()
{
    Date dt(5, 6, 92);
    cout << dt;
}
```

```Output
5/6/92
```

## <a name="remarks"></a>Uwagi

Przeciążony operator zwraca odwołanie do oryginalnego `ostream` obiektu, co oznacza, że można łączyć wstawienia:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Zobacz też

[Strumienie wyjściowe](../standard-library/output-streams.md)
