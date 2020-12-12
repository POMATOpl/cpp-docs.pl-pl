---
description: Dowiedz się więcej na temat klasy is_nothrow_move_constructible
title: is_nothrow_move_constructible — klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 9ab9d1dfdba532bfda3111831f389a94a49af936
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323599"
---
# <a name="is_nothrow_move_constructible-class"></a>is_nothrow_move_constructible — klasa

Testuje, czy typ ma **`nothrow`** Konstruktor przenoszenia.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* ma Konstruktor przenoszenia nothrow, w przeciwnym razie ma wartość false.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
