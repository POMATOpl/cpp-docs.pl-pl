---
description: Dowiedz się więcej na temat klasy is_nothrow_default_constructible
title: is_nothrow_default_constructible —  klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
ms.openlocfilehash: bbfadf10048175472c10f264856cdb519896b65f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230799"
---
# <a name="is_nothrow_default_constructible-class"></a>is_nothrow_default_constructible —  klasa

Testuje, czy typ ma niezgłaszany domyślny Konstruktor.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_nothrow_default_constructible;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* ma konstruktora domyślnego nothrow, w przeciwnym razie zawiera wartość false. Wystąpienie predykatu typu jest równoważne z `is_nothrow_constructible<Ty>` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
