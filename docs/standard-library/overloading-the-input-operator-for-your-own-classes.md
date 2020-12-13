---
description: 'Dowiedz się więcej na temat: przeciążanie &gt; &gt; operatora dla własnych klas'
title: Przeciążanie &gt; &gt; operatora dla własnych klas
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 4de7c16dd1c42f85f169da50f11a514eb245b47c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340856"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Przeciążanie &gt; &gt; operatora dla własnych klas

Strumienie wejściowe używają operatora wyodrębniania ( `>>` ) dla typów standardowych. Można napisać podobne operatory wyodrębniania dla własnych typów; sukces zależy od użycia pustego miejsca.

Oto przykład operatora wyodrębniania dla `Date` przedstawionej wcześniej klasy:

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Zobacz też

[Strumienie wejściowe](../standard-library/input-streams.md)
