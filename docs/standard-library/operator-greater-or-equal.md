---
description: 'Dowiedz się więcej na temat: operator&gt;='
title: zakład&gt;=
ms.date: 11/04/2016
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
ms.openlocfilehash: 1821647ebb281020cef1798cf056fbf816aa855c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297073"
---
# <a name="operatorgt"></a>zakład&gt;=

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Operator przeciążeń **>=** do porównania dwóch obiektów [kontenera](../standard-library/sample-container-class.md)szablonu klasy.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator>=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość `!(left < right)`.

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)
