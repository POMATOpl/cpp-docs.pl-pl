---
description: 'Dowiedz się więcej o: Klasa warunkowa'
title: conditional — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: f8edbd7341598957ecbe8b0822a832973f0e06a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324974"
---
# <a name="conditional-class"></a>conditional — Klasa

Wybiera jeden z dwóch typów, w zależności od określonego warunku.

## <a name="syntax"></a>Składnia

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Parametry

*B*\
Wartość, która określa wybrany typ.

*Połączeń*\
Wynik typu, gdy B ma wartość true.

*T2*\
Wynik typu, gdy B ma wartość false.

## <a name="remarks"></a>Uwagi

Element członkowski szablonu typedef `conditional<B, T1, T2>::type` szacuje się na *T1* , gdy *b* szacuje się w **`true`** , i przyjmuje wartość *T2* , gdy *b* szacuje się **`false`** .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
