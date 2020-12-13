---
description: 'Dowiedz się więcej na temat: operator = = ( &lt; przykład kontenera &gt; )'
title: operator = = ( &lt; przykładowy kontener &gt; )
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: b2fb296feb76536c28dd45e631af8071efa16939
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337977"
---
# <a name="operator-ltsample-containergt"></a>operator = = ( &lt; przykładowy kontener &gt; )

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Przeciążenia `operator==` do porównywania dwóch obiektów [kontenera](../standard-library/sample-container-class.md)szablonów klas.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca `left.` [](../standard-library/container-class-size.md) `== right.size && equal(left.` [](../standard-library/container-class-begin.md) `, left.` [koniec](../standard-library/container-class-end.md)rozmiaru `, right.begin)` .

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)
