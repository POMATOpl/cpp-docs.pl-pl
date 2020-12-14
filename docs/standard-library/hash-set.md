---
description: 'Dowiedz się więcej na temat: &lt; hash_set&gt;'
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
- std::<hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: 353ec0a4f57662380e912893ca60c93025e577af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231789"
---
# <a name="lthash_setgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Ten nagłówek jest przestarzały. Alternatywą jest [<unordered_set>](../standard-library/unordered-set.md).

Definiuje szablony klas kontenerów hash_set i hash_multiset i ich szablony pomocnicze.

## <a name="syntax"></a>Składnia

```cpp
#include <hash_set>
```

## <a name="remarks"></a>Uwagi

### <a name="operators"></a>Operatory

|Wersja Hash_set|Wersja Hash_multiset|Opis|
|-----------------------|----------------------------|-----------------|
|[operator! = (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator! = (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Testuje, czy obiekt hash_set lub hash_multiset po lewej stronie operatora nie jest równy obiektowi hash_set lub hash_multiset po prawej stronie.|
|[operator = = (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator = = (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Testuje, czy obiekt hash_set lub hash_multiset po lewej stronie operatora jest równy obiektowi hash_set lub hash_multiset po prawej stronie.|

### <a name="specialized-template-functions"></a>Specialized Template — Funkcje

|Wersja Hash_set|Wersja Hash_multiset|Opis|
|-----------------------|----------------------------|-----------------|
|[Zamień (hash_set)](../standard-library/hash-set-functions.md#swap)|[Zamień (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|Wymienia elementy dwóch hash_sets lub hash_multisets.|

### <a name="classes"></a>Klasy

|Klasa|Opis|
|-|-|
|[Klasa hash_compare](../standard-library/hash-compare-class.md)|Opisuje obiekt, który może być używany przez dowolny kontener asocjacyjnych skrótów — hash_map, hash_multimap, hash_set lub hash_multiset — jako domyślny `Traits` obiekt parametru do porządkowania i mieszania elementów, które zawierają.|
|[Klasa hash_set](../standard-library/hash-set-class.md)|Służy do przechowywania i szybkiego pobierania danych z kolekcji, w której wartości zawartych elementów są unikatowe i służą jako wartości klucza.|
|[Klasa hash_multiset](../standard-library/hash-multiset-class.md)|Służy do przechowywania i szybkiego pobierania danych z kolekcji, w której wartości zawartych elementów są unikatowe i służą jako wartości klucza.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
