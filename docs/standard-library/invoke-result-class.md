---
description: Dowiedz się więcej na temat klasy invoke_result
title: Klasa invoke_result
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: 4204ff1b0b8d38eab4b7d8c0de4709b90e12f5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231500"
---
# <a name="invoke_result-class"></a>Klasa invoke_result

Określa zwracany typ wywoływanego typu, który przyjmuje określone typy argumentów w czasie kompilacji. Dodano w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parametry

*Żądanie*\
Typ możliwy do zapytania.

*Argumentów*\
Typy listy argumentów dla wywoływanego typu do zapytania.

## <a name="remarks"></a>Uwagi

Użyj tego szablonu, aby określić typ wyniku możliwego *do przeprowadzenia (**args*...) w czasie kompilacji *, gdzie możliwe* jest dokończenie i wszystkie typy w *args* , tablica nieznanej granicy lub prawdopodobnie kwalifikowana CV **`void`** . `type`Element członkowski szablonu klasy nazywa zwracany typ, który jest wywoływany w przypadku wywołania przy użyciu argumentów argumenty....  `type`Element członkowski jest definiowany tylko wtedy *, gdy* można wywołać wywoływanie przy użyciu argumentów argumenty... w nieoszacowanym kontekście. W przeciwnym razie szablon klasy nie ma elementu członkowskiego `type` , który umożliwia testowanie SFINAE na określonym zestawie typów argumentów w czasie kompilacji.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[wywołuje](functional-functions.md#invoke)
