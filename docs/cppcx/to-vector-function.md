---
description: 'Dowiedz się więcej o: funkcja to_vector'
title: Funkcja to_vector
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 77d6bee58a793946f91bc03ba4afed35aa7252cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307590"
---
# <a name="to_vector-function"></a>Funkcja to_vector

Zwraca, `std::vector` której wartość jest taka sama jak kolekcja określona dla parametru IVector lub IVectorView.

## <a name="syntax"></a>Składnia

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Parametr typu szablonu.

*v*<br/>
Interfejs IVector lub IVectorView, który zapewnia dostęp do bazowego obiektu Vector lub VectorView.

### <a name="return-value"></a>Wartość zwracana

### <a name="requirements"></a>Wymagania

**Nagłówek:** Collection. h

**Przestrzeń nazw:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation:: Collections, przestrzeń nazw](../cppcx/windows-foundation-collections-namespace-c-cx.md)
