---
description: Dowiedz się więcej o metodzie CompareStringOrdinal
title: CompareStringOrdinal — Metoda
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: 1994d0f3ec4104e27094de10255194a911ae2945
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282851"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal — Metoda

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Parametry

*LHS*<br/>
Pierwszy HSTRING do porównania.

*RHS*<br/>
Druga HSTRING do porównania.

## <a name="return-value"></a>Wartość zwracana

|Wartość|Warunek|
|-----------|---------------|
|-1|*LHS* jest mniejszy niż *RHS*.|
|0|*LHS* równa się *RHS*.|
|1|wartość *LHS* jest większa niż *RHS*.|

## <a name="remarks"></a>Uwagi

Porównuje dwa określone obiekty HSTRING i zwraca liczbę całkowitą, która wskazuje ich położenie względne w kolejności sortowania.

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL:: otoki::D etails przestrzeń nazw](microsoft-wrl-wrappers-details-namespace.md)
