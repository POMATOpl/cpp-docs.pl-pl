---
description: Dowiedz się więcej na temat klasy is_trivially_constructible
title: Klasa is_trivially_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 4a5c3e20366c4e87aa731c6d6a69787286b947b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247634"
---
# <a name="is_trivially_constructible-class"></a>Klasa is_trivially_constructible

Testuje, czy typ jest bardzo konstrukcyjną, gdy są używane określone typy argumentów.

## <a name="syntax"></a>Składnia

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

*Argumentów*\
Typy argumentów do dopasowania w konstruktorze *T*.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest niekonstrukcyjnąy przy użyciu typów argumentów w argumentach *, w przeciwnym* razie ma wartość false. Typ *T* jest niekonstrukcyjnąy, jeśli definicja zmiennej `T t(std::declval<Args>()...);` jest poprawnie sformułowana i jest znana do wywołania braku prostych operacji. Zarówno *T* , jak i wszystkie typy w *args* muszą być pełnymi typami **`void`** lub tablicami nieznanego powiązania.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
