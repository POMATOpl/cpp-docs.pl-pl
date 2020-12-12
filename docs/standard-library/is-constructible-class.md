---
description: Dowiedz się więcej na temat klasy is_constructible
title: Klasa is_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: 66d17141693933850ce78dc15abe108664d56c8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323818"
---
# <a name="is_constructible-class"></a>Klasa is_constructible

Testuje, czy typ jest konstrukcyjną, gdy są używane określone typy argumentów.

## <a name="syntax"></a>Składnia

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

*Argumentów*\
Typy argumentów do dopasowania w konstruktorze *T*.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest konstrukcyjną przy użyciu typów argumentów w *args*, w przeciwnym razie ma wartość false. Typ *T* jest konstrukcyjną, jeśli definicja zmiennej `T t(std::declval<Args>()...);` jest poprawnie sformułowana. Zarówno *T* , jak i wszystkie typy w *args* muszą być pełnymi typami **`void`** lub tablicami nieznanego powiązania.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
