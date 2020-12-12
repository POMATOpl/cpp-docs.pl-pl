---
description: Dowiedz się więcej na temat klasy make_unsigned
title: make_unsigned — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 3767a9971c17667b5d2fe545e524f563df2a7f42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277521"
---
# <a name="make_unsigned-class"></a>make_unsigned — Klasa

Ustawia typ lub najmniejszy typ bez znaku, który jest większy niż lub równy rozmiarowi do typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie modyfikatora typu zawiera zmodyfikowany typ, *który ma* `is_unsigned<T>` wartość true. W przeciwnym razie jest to najmniejszy podpisany typ, `ST` dla którego `sizeof (T) <= sizeof (ST)` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
