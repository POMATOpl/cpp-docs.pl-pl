---
description: 'Dowiedz się więcej o: kontener Class:: swap'
title: Kontener Class::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: a38dd6d14ada3ad50927060ccec1542ebf2fd4ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233360"
---
# <a name="container-classswap"></a>Kontener Class::swap

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Zamienia kontrolowane sekwencje między **\* tym** i argumentem.

## <a name="syntax"></a>Składnia

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Uwagi

Jeśli jest **\* to możliwe. Pobierz program \_ przydzielający = =** _Right_**.get_allocator**, spowoduje to wymianę w stałym czasie. W przeciwnym razie wykonuje wiele przypisań elementów i wywołań konstruktora proporcjonalnie do liczby elementów w dwóch kontrolowanej sekwencji.

## <a name="see-also"></a>Zobacz też

[Przykładowa Klasa kontenera](../standard-library/sample-container-class.md)
