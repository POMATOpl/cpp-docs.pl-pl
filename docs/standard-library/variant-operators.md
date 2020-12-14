---
description: 'Dowiedz się więcej o: &lt; &gt; Operatory wariantów'
title: '&lt;&gt;Operatory wariantów'
ms.date: 04/04/2019
f1_keywords:
- variant/std::operator!=
- variant/std::operator==
- variant/std::operatoroperator&gt;
- variant/std::operatoroperator&gt=;
- variant/std::operatoroperator&lt;
- variant/std::operatoroperator&lt;=
helpviewer_keywords:
- std::operator!= (variant)
- std::operator== (variant)
- std::operatoroperator&gt; (variant)
- std::operatoroperator&gt=; (variant)
- std::operatoroperator&lt; (variant)
- std::operatoroperator&lt;= (variant)
ms.openlocfilehash: 3315c73ea529ad7ade4f32be3784a43bda07ac26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312829"
---
# <a name="ltvariantgt-operators"></a>&lt;&gt;Operatory wariantów

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

Testuje, czy obiekt listy do przodu po lewej stronie operatora jest równy obiektowi listy do przodu po prawej stronie.

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operator"></a><a name="op_neq"></a> operator! =

Testuje, czy obiekt listy do przodu po lewej stronie operatora nie jest równy obiektowi listy do przodu po prawej stronie.

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt"></a> zakład&lt;

Testuje, czy obiekt listy do przodu po lewej stronie operatora jest mniejszy niż obiekt listy do przodu po prawej stronie.

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> zakład&lt;=

Testuje, czy obiekt listy do przodu po lewej stronie operatora jest mniejszy niż lub równy obiektowi listy do przodu po prawej stronie.

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt"></a> zakład&gt;

Testuje, czy obiekt listy do przodu po lewej stronie operatora jest większy niż obiekt listy do przodu po prawej stronie.

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> zakład&gt;=

Testuje, czy obiekt listy do przodu po lewej stronie operatora jest większy niż lub równy obiektowi listy do przodu po prawej stronie.

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
