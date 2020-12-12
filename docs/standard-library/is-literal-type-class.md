---
description: Dowiedz się więcej na temat klasy is_literal_type
title: Klasa is_literal_type
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 97cb609c5a42bed0be205b1b51ff901d3e366bb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323689"
---
# <a name="is_literal_type-class"></a>Klasa is_literal_type

Testuje, czy typ może być używany jako **`constexpr`** zmienna, czy być skonstruowany, używany przez lub zwrócony z **`constexpr`** funkcji.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest *typem literału*, w przeciwnym razie ma wartość false. Typ literału to **`void`** , typ skalarny, typ referencyjny, tablica typu literału lub typ klasy literału. Typ klasy literału jest typem klasy, który ma prosty destruktor, jest typem agregującym lub ma co najmniej jeden Konstruktor, który nie należy do przenoszenia, **`constexpr`** a wszystkie jego klasy bazowe i niestatyczne elementy członkowskie danych są typami literałów nietrwałych. Chociaż typ literału zawsze jest typem literału, pojęcie typu literału zawiera wszystkie elementy, które kompilator może oszacować jako **`constexpr`** w czasie kompilacji.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
