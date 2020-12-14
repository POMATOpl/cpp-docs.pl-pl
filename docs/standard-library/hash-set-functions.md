---
description: Dowiedz się więcej na temat &lt; &gt; funkcji hash_set
title: '&lt;&gt;funkcje hash_set'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 7040325f3af26052306b1ebd90f1919d96dcbf19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231799"
---
# <a name="lthash_setgt-functions"></a>&lt;&gt;funkcje hash_set

[wymiany](#swap)\
[Zamień (hash_multiset)](#swap_hash_multiset)

## <a name="swap"></a><a name="swap"></a> wymiany

> [!NOTE]
> Ten interfejs API jest nieaktualny. Alternatywą jest [klasa unordered_set](../standard-library/unordered-set-class.md).

Wymienia elementy dwóch hash_sets.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Hash_set dostarcza elementów do wymiany lub hash_set których elementy mają być wymieniane z *pozostałymi* hash_setami.

*lewym*\
Hash_set, których elementy mają być wymieniane z tymi hash_set *prawo*.

### <a name="remarks"></a>Uwagi

`swap`Funkcja szablonu jest algorytm wyspecjalizowany dla klasy kontenera hash_set do wykonywania operacji swap funkcji składowej `left.` [](../standard-library/hash-set-class.md#swap)( `right` ). Jest to wystąpienie częściowego porządkowania szablonów funkcji przez kompilator. Gdy funkcje szablonu są przeciążone w taki sposób, że dopasowanie szablonu z wywołaniem funkcji nie jest unikatowe, kompilator wybierze najbardziej wyspecjalizowaną wersję funkcji szablonu. Ogólna wersja funkcji szablonu

**\<class T>Unieważnij zamianę szablonu (t&, t&),**

w klasie algorytmu działa przez przypisanie i jest operacją powolnej. Wyspecjalizowana wersja w każdym kontenerze jest znacznie szybsza, ponieważ może pracować z wewnętrzną reprezentacją klasy Container.

### <a name="example"></a>Przykład

Zobacz przykład kodu dla klasy składowej [hash_set:: swap](../standard-library/hash-set-class.md#swap) dla przykładu korzystającego z wersji szablonu `swap` .

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a> Zamień (hash_multiset)

> [!NOTE]
> Ten interfejs API jest nieaktualny. Alternatywą jest [klasa unordered_set](../standard-library/unordered-set-class.md).

Wymienia elementy dwóch hash_multisets.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Hash_multiset dostarcza elementów do wymiany lub hash_multiset których elementy mają być wymieniane z *pozostałymi* hash_multisetami.

*lewym*\
Hash_multiset, których elementy mają być wymieniane z tymi hash_multiset *prawo*.

### <a name="remarks"></a>Uwagi

`swap`Funkcja szablonu jest algorytm wyspecjalizowany dla klasy kontenera hash_multiset do wykonywania operacji swap funkcji składowej `left.` [](../standard-library/hash-multiset-class.md#swap)( `right` ). Jest to wystąpienie częściowego porządkowania szablonów funkcji przez kompilator. Gdy funkcje szablonu są przeciążone w taki sposób, że dopasowanie szablonu z wywołaniem funkcji nie jest unikatowe, kompilator wybierze najbardziej wyspecjalizowaną wersję funkcji szablonu. Ogólna wersja funkcji szablonu

**\<class T>Unieważnij zamianę szablonu (t&, t&),**

w klasie algorytmu działa przez przypisanie i jest operacją powolnej. Wyspecjalizowana wersja w każdym kontenerze jest znacznie szybsza, ponieważ może pracować z wewnętrzną reprezentacją klasy Container.

### <a name="example"></a>Przykład

Zobacz przykład kodu dla klasy składowej [hash_multiset:: swap](../standard-library/hash-multiset-class.md#swap) dla przykładu korzystającego z wersji szablonu `swap` .

## <a name="see-also"></a>Zobacz też

[<hash_set>](../standard-library/hash-set.md)
