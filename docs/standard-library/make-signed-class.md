---
description: Dowiedz się więcej na temat klasy make_signed
title: make_signed — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: 2f11fe3223e6193613772d2c4abbf0182215a17d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277560"
---
# <a name="make_signed-class"></a>make_signed — Klasa

Ustawia typ lub najmniejszy typ podpisany o wartości większej lub równej rozmiarowi do typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie modyfikatora typu zawiera zmodyfikowany typ, *który ma* `is_signed<T>` wartość true. W przeciwnym razie jest to najmniejszy typ bez znaku, `UT` dla którego `sizeof (T) <= sizeof (UT)` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
