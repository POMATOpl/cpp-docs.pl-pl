---
description: 'Dowiedz się więcej o: funkcja back_inserter'
title: Funkcja back_inserter
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: d2483c9947fbf3a7bc04024221ec6e582e416f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223584"
---
# <a name="back_inserter-function"></a>Funkcja back_inserter

Zwraca iterator, który jest używany do wstawiania elementów na końcu określonej kolekcji.

## <a name="syntax"></a>Składnia

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Parametr typu szablonu.

*v*<br/>
Wskaźnik interfejsu, który zapewnia dostęp do źródłowej kolekcji.

### <a name="return-value"></a>Wartość zwracana

Iterator.

### <a name="requirements"></a>Wymagania

**Nagłówek:** Collection. h

**Przestrzeń nazw:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation:: Collections, przestrzeń nazw](../cppcx/windows-foundation-collections-namespace-c-cx.md)
