---
description: Dowiedz się więcej na temat klasy value_compare
title: value_compare — Klasa
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: d77412b2d979ef4db84621df1b0c94191f3d2a5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211716"
---
# <a name="value_compare-class"></a>value_compare — Klasa

Udostępnia obiekt funkcji, który może porównać elementy hash_map, porównując wartości ich kluczy, aby określić ich względną kolejność w hash_map.

## <a name="syntax"></a>Składnia

```cpp
class value_compare
    : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
        const value_type& left,
        const value_type& right) const
    {
        return (comp(left.first, right.first));
    }

protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>Uwagi

Kryteria porównania podane przez value_compare między `value_types` całymi elementami zawartymi w hash_map jest wywołane z porównania między kluczami odpowiednich elementów przez konstrukcję klasy pomocniczej. Operator funkcji składowej używa obiektu `comp` typu `key_compare` przechowywanego w obiekcie funkcji dostarczonym przez value_compare, aby porównać składniki klucza sortowania dwóch elementów.

Dla hash_sets i hash_multisets, które są prostymi kontenerami, w których wartości klucza są identyczne z wartościami elementu, value_compare jest równoważne `key_compare` ; dla hash_maps i hash_multimaps nie są, ponieważ wartość `pair` elementów Type nie jest taka sama jak wartość klucza elementu.

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [hash_map:: value_comp](../standard-library/hash-map-class.md#value_comp) , aby zapoznać się z przykładem sposobu deklarowania i używania value_compare.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<hash_map>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[Struktura binary_function](../standard-library/binary-function-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
