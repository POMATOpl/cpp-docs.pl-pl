---
description: Dowiedz się więcej na temat klasy is_move_assignable
title: Klasa is_move_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: ccca3eb1da646bad9e55222a23b5ae8d511d3bb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230864"
---
# <a name="is_move_assignable-class"></a>Klasa is_move_assignable

Testuje, czy można przenieść typ.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Typ jest przesuwany do przypisania, jeśli odwołanie rvalue do typu może zostać przypisane do odwołania do typu. Predykat typu jest równoważny z `is_assignable<T&, T&&>` . Przenieś typy z możliwością przypisania zawierają typy skalarne i typy klas, które mają zdefiniowane przez użytkownika operatory przypisania przenoszenia.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
