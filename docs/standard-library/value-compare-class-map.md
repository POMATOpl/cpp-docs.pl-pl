---
description: 'Dowiedz się więcej na temat: value_compare Class ( &lt; map &gt; )'
title: Klasa value_compare ( &lt; Mapa &gt; )
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: c5b7ba865606e0bc5a5c8238de72824f9061c1b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312816"
---
# <a name="value_compare-class-ltmapgt"></a>Klasa value_compare ( &lt; Mapa &gt; )

Udostępnia obiekt funkcji, który może porównać elementy mapy przez porównanie wartości ich kluczy w celu określenia ich względnej kolejności w mapie.

## <a name="syntax"></a>Składnia

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>Uwagi

Kryterium porównania dostarczone przez `value_compare` między `value_types` całymi elementami zawartymi w mapie jest wywołane z porównania między kluczami odpowiednich elementów przez konstrukcję klasy pomocniczej. Operator funkcji składowej używa obiektu `comp` typu `key_compare` przechowywanego w obiekcie funkcji dostarczonym przez, `value_compare` Aby porównać składniki klucza sortowania dwóch elementów.

Dla zestawów i zestawów wielozbiorów, które są prostymi kontenerami, w których wartości klucza są identyczne z wartościami elementu, `value_compare` są równoważne `key_compare` ; w przypadku map i map wielowartościowych nie są, ponieważ wartość `pair` elementów Type nie jest taka sama jak wartość klucza elementu.

## <a name="example"></a>Przykład

Zapoznaj się z przykładem na [value_comp](../standard-library/map-class.md#value_comp) , aby zapoznać się z przykładem sposobu deklarowania i używania `value_compare` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<map>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Struktura binary_function](../standard-library/binary-function-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
