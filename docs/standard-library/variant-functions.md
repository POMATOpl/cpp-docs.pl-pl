---
title: '&lt;Wariant&gt; funkcji'
ms.date: 04/04/2019
f1_keywords:
- variant/std::get
- variant/std::get_if
- variant/std::holds_alternative
- variant/std::visit
ms.openlocfilehash: d558eb086e076ba22722080b0c19f3d5733136d2
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267869"
---
# <a name="ltvariantgt-functions"></a>&lt;Wariant&gt; funkcji

## <a name="get"></a> Pobierz

Pobiera typ variant obiektu.

```cpp
template <size_t I, class... Types>
    constexpr variant_alternative_t<I, variant<Types...>>& get(variant<Types...>&);
template <size_t I, class... Types>
    constexpr variant_alternative_t<I, variant<Types...>>&& get(variant<Types...>&&);
template <size_t I, class... Types>
    constexpr const variant_alternative_t<I, variant<Types...>>& get(const variant<Types...>&);
template <size_t I, class... Types>
    constexpr const variant_alternative_t<I, variant<Types...>>&& get(const variant<Types...>&&);
template <class T, class... Types>
    constexpr T& get(variant<Types...>&);
template <class T, class... Types>
    constexpr T&& get(variant<Types...>&&);
template <class T, class... Types>
    constexpr const T& get(const variant<Types...>&);
template <class T, class... Types>
    constexpr const T&& get(const variant<Types...>&&);
```

## <a name="get_if"></a> get_if

Pobiera typ variant obiektu, jeśli taki istnieje.

```cpp
template <size_t I, class... Types>
    constexpr add_pointer_t<variant_alternative_t<I, variant<Types...>>> get_if(variant<Types...>*) noexcept;
template <size_t I, class... Types>
    constexpr add_pointer_t<const variant_alternative_t<I, variant<Types...>>> get_if(const variant<Types...>*) noexcept;
template <class T, class... Types>
    constexpr add_pointer_t<T> get_if(variant<Types...>*) noexcept;
template <class T, class... Types>
    constexpr add_pointer_t<const T> get_if(const variant<Types...>*) noexcept;
```

## <a name="holds_alternative"></a> holds_alternative

Zwróć **true** istnienia wariant.

```cpp
template <class T, class... Types>
    constexpr bool holds_alternative(const variant<Types...>&) noexcept;
```

## <a name="swap"></a> swap

```cpp
template <class... Types>
    void swap(variant<Types...>&, variant<Types...>&) noexcept(see below);
```

## <a name="variant_npos"></a> variant_npos

```cpp
namespace std {
    inline constexpr size_t variant_npos = -1;
}
```

## <a name="visit"></a> Odwiedź stronę

Przechodzi do następnego **wariant**.

```cpp
template <class Visitor, class... Variants>
    constexpr see below
        visit(Visitor&&, Variants&&...);
```
