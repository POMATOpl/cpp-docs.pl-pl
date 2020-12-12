---
description: Dowiedz się więcej na temat klasy result_of
title: result_of — Klasa
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: 2aba6b073309be064b9ff0edc7bffa4d8d0098e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273907"
---
# <a name="result_of-class"></a>result_of — Klasa

Określa zwracany typ wywoływanego typu, który przyjmuje określone typy argumentów. Dodano w języku C++ 14, przestarzałe w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>Parametry

*Fn*\
Typ możliwy do zapytania.

*ArgTypes*\
Typy listy argumentów dla wywoływanego typu do zapytania.

## <a name="remarks"></a>Uwagi

Użyj tego szablonu, aby określić w czasie kompilacji typ wyniku `Fn` ( `ArgTypes` ), gdzie *Fn* jest typem możliwym do wywołania, odwołaniem do funkcji lub odwołaniem do żądanego typu, wywoływane przy użyciu listy argumentów typów w *ArgTypes*. `type`Element członkowski szablonu klasy nazywa typ wyniku, `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` Jeśli wyrażenie nieoceniane `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` jest poprawnie sformułowane. W przeciwnym razie szablon klasy nie ma żadnego elementu członkowskiego `type` . Typ *Fn* i wszystkie typy w pakiecie parametrów *ArgTypes* muszą być kompletnymi typami, **`void`** lub tablicami nieznanego powiązania. Przestarzałe na rzecz [invoke_result](invoke-result-class.md) w języku c++ 17.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[invoke_result, klasa](invoke-result-class.md)
