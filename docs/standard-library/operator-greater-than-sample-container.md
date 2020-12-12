---
description: 'Dowiedz się więcej na temat: operator &gt; ( &lt; przykład kontenera &gt; )'
title: operator &gt; ( &lt; przykładowy kontener &gt; )
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: 4a8282b3cac493bbf0c2bcb24b8db44df45168f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114965"
---
# <a name="operatorgt-ltsample-containergt"></a>operator &gt; ( &lt; przykładowy kontener &gt; )

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

**Operator przeciążenia>** do porównywania dwóch obiektów [kontenera](../standard-library/sample-container-class.md)szablonu klasy.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość `right < left`.

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)
