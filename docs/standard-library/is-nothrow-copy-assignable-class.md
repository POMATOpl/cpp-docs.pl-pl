---
description: Dowiedz się więcej na temat klasy is_nothrow_copy_assignable
title: is_nothrow_copy_assignable Class
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 43618158e33a393012a9f7a4a3ad14c816e3cd6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230812"
---
# <a name="is_nothrow_copy_assignable-class"></a>is_nothrow_copy_assignable Class

Testuje, czy typ ma operator przypisania kopiowania, który jest znany przez kompilator, aby nie zgłaszać.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true dla typu referencyjnego *T* `is_nothrow_assignable<T&, const T&>` , gdzie ma wartość true; w przeciwnym razie ma wartość false.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)
