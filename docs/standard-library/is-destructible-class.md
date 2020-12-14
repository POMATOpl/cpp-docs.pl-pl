---
description: Dowiedz się więcej na temat klasy is_destructible
title: Klasa is_destructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: fcd41c292c0054553b165529a85e7b23312d3c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231163"
---
# <a name="is_destructible-class"></a>Klasa is_destructible

Testuje, czy typem jest zniszczalnych.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest typem zniszczalnych, w przeciwnym razie zawiera wartość false. Typy zniszczalnych to typy odwołań, typy obiektów i typy, w których dla niektórych typów, które `U` `remove_all_extents_t<T>` są równe nieocenianego operandu, `std::declval<U&>.~U()` są poprawnie sformułowane. Inne typy, w tym niekompletne typy, **`void`** i typy funkcji, nie są typami zniszczalnych.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
