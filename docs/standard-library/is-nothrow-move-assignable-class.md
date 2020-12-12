---
description: Dowiedz się więcej na temat klasy is_nothrow_move_assignable
title: Klasa is_nothrow_move_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
ms.openlocfilehash: 77d61ff79d56ff1caee2d856ac4d947821c16946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230760"
---
# <a name="is_nothrow_move_assignable-class"></a>Klasa is_nothrow_move_assignable

Testuje, czy typ ma **`nothrow`** operator przypisania przenoszenia.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* ma operator przypisania operacji przenoszenia nothrow, w przeciwnym razie ma wartość false.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
