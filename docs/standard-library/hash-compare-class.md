---
description: Dowiedz się więcej na temat klasy hash_compare
title: hash_compare — Klasa
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 510de9901e58e130a53410b688c22324714b9962
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231943"
---
# <a name="hash_compare-class"></a>hash_compare — Klasa

Szablon klasy opisuje obiekt, który może być używany przez dowolny kontener asocjacyjnych skrótów — hash_map, hash_multimap, hash_set lub hash_multiset — jako domyślny obiekt parametru **cech** w celu uporządkowania i mieszania elementów, które zawierają.

## <a name="syntax"></a>Składnia

Klasa hash_compare {cechuje się; Public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare (); hash_compare (cechy pred); size_t operator () (klucz const& Key) const; operator logiczny () (klucz const& Klucz1, const Key& klucz2) const;};

## <a name="remarks"></a>Uwagi

Każdy element skrótu asocjacyjny kontener przechowuje obiekt cech mieszania typu `Traits` (parametr szablonu). Można utworzyć klasę z specjalizacji hash_compare, aby selektywnie zastępować pewne funkcje i obiekty, lub podać własną wersję tej klasy, jeśli spełniasz pewne wymagania minimalne. W odniesieniu do obiektu hash_comp typu `hash_compare<Key, Traits>` , w powyższych kontenerach wymagane jest następujące zachowanie:

- Dla wszystkich wartości `key` typu `Key` , wywołanie **hash_comp**( `key` ) służy jako funkcja skrótu, która zwraca rozkład wartości typu `size_t` . Funkcja dostarczana przez hash_compare zwraca wartość `key` .

- Dla każdej wartości `key1` typu `Key` , która poprzedza `key2` sekwencję i ma tę samą wartość skrótu (wartość zwróconą przez funkcję mieszania), **hash_comp**( `key2` , `key1` ) ma wartość false. Funkcja musi nałożyć całkowitą kolejność na wartości typu `Key` . Funkcja dostarczana przez hash_compare zwraca wartość *COMP*( `key2` , `key1` ), `,` gdzie *COMP* jest przechowywanym obiektem typu `Traits` , który można określić podczas konstruowania hash_comp obiektu. Dla domyślnego `Traits` typu parametru `less<Key>` Sortuj klucze nigdy nie zmniejszają wartości.

- Stała całkowita `bucket_size` Określa średnią liczbę elementów na "zasobnik" (wpis w tabeli skrótów), którą kontener powinien próbować nie przekraczać. Musi być większa od zera. Wartość dostarczona przez hash_compare to 4.

- Stała całkowita `min_buckets` określa minimalną liczbę przedziałów do utrzymania w tabeli skrótów. Musi być potęgą liczby 2 i większa od zera. Wartość dostarczona przez hash_compare to 8.

## <a name="example"></a>Przykład

Zobacz przykłady [hash_map:: hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap:: hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set:: hash_set](../standard-library/hash-set-class.md#hash_set)i [hash_multiset:: hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset), aby poznać Przykłady sposobu deklarowania i używania hash_compare.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<hash_map>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
