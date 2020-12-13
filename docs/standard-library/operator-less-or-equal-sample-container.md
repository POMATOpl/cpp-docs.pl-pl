---
description: 'Dowiedz się więcej na temat: operator &lt; = ( &lt; przykład kontenera &gt; )'
title: operator &lt; = ( &lt; przykład kontenera &gt; )
ms.date: 11/04/2016
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
ms.openlocfilehash: 4455efcbd5b3ccca262265f44414b46d3e97f57d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337989"
---
# <a name="operatorlt-ltsample-containergt"></a>operator &lt; = ( &lt; przykład kontenera &gt; )

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Operator przeciążeń **<=** do porównania dwóch obiektów [kontenera](../standard-library/sample-container-class.md)szablonu klasy.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość `!(right < left)`.

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)
