---
description: Dowiedz się więcej o klasie zaniku
title: decay — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 6f6a1ebd31af44a48eaf400f9dccefdbd8ca3d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324604"
---
# <a name="decay-class"></a>decay — Klasa

Tworzy typ jako przekazaną przez wartość. Sprawia, że typ nie jest odwołaniem, niestałym, nietrwałym lub tworzy wskaźnik do typu z funkcji lub typu tablicy.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Użyj szablonu pozostałej w celu utworzenia typu wynikowego, tak jakby typ został przekazano przez wartość jako argument. Element typedef składowej szablonu klasy `type` zawiera zmodyfikowany typ, który jest zdefiniowany w następujących etapach:

- Typ `U` jest zdefiniowany jako `remove_reference<T>::type` .

- Jeśli `is_array<U>::value` ma wartość true, modyfikowany `type` jest typ `remove_extent<U>::type *` .

- W przeciwnym razie, jeśli `is_function<U>::value` ma wartość true, zmodyfikowany typ `type` to `add_pointer<U>::type` .

- W przeciwnym razie zmodyfikowany typ `type` to `remove_cv<U>::type` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
