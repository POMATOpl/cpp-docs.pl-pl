---
description: 'Dowiedz się więcej na temat: operator &lt; ( &lt; przykład kontenera &gt; )'
title: operator &lt; ( &lt; przykładowy kontener &gt; )
ms.date: 11/04/2016
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
ms.openlocfilehash: e7bba9be33a2dc4dea6257b159966c867bb33929
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176486"
---
# <a name="operatorlt-ltsample-containergt"></a>operator &lt; ( &lt; przykładowy kontener &gt; )

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

**Operator przeciążenia<** do porównywania dwóch obiektów [kontenera](../standard-library/sample-container-class.md)szablonu klasy.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość `lexicographical_compare(left.begin, left.end, right.begin, right.end)`.

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)\
[zaczną](../standard-library/container-class-begin.md)\
[punktów](../standard-library/container-class-end.md)
