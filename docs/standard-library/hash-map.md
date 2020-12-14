---
description: 'Dowiedz się więcej na temat: &lt; hash_map&gt;'
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: b3e46a3f8ef1638525414c1a1414c4eb6e418c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231878"
---
# <a name="lthash_mapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Ten nagłówek jest przestarzały. Alternatywą jest [\<unordered_map>](unordered-map.md) .

Definiuje szablony klas kontenerów hash_map i hash_multimap i ich szablony pomocnicze.

## <a name="syntax"></a>Składnia

```cpp
#include <hash_map>
```

### <a name="operators"></a>Operatory

|Wersja Hash_map|Wersja Hash_multimap|Opis|
|-----------------------|----------------------------|-----------------|
|[operator! = (hash_map)](hash-map-operators.md#op_neq)|[operator! = (hash_multimap)](hash-map-operators.md#op_neq_mm)|Testuje, czy obiekt hash_map lub hash_multimap po lewej stronie operatora nie jest równy obiektowi hash_map lub hash_multimap po prawej stronie.|
|[operator = = (hash_map)](hash-map-operators.md#op_eq_eq)|[operator = = (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Testuje, czy obiekt hash_map lub hash_multimap po lewej stronie operatora jest równy obiektowi hash_map lub hash_multimap po prawej stronie.|

### <a name="specialized-template-functions"></a>Specialized Template — Funkcje

|Wersja Hash_map|Wersja Hash_multimap|Opis|
|-----------------------|----------------------------|-----------------|
|[Zamień (hash_map)](hash-map-class.md#swap)|[Zamień (hash_multimap)](hash-multimap-class.md#swap)|Wymienia elementy dwóch hash_maps lub hash_multimaps.|

### <a name="classes"></a>Klasy

|Klasa|Opis|
|-|-|
|[Klasa hash_compare](hash-compare-class.md)|Opisuje obiekt, który może być używany przez dowolny kontener asocjacyjnych skrótów — hash_map, hash_multimap, hash_set lub hash_multiset — jako domyślny `Traits` obiekt parametru do porządkowania i mieszania elementów, które zawierają.|
|[Klasa value_compare](value-compare-class.md)|Udostępnia obiekt funkcji, który może porównać elementy hash_map, porównując wartości ich kluczy, aby określić ich względną kolejność w hash_map.|
|[Klasa hash_map](hash-map-class.md)|Służy do przechowywania i szybkiego pobierania danych z kolekcji, w której każdy element jest parą, która ma klucz sortowania, którego wartość jest unikatowa i skojarzona wartość danych.|
|[Klasa hash_multimap](hash-multimap-class.md)|Używany do przechowywania i szybkiego pobierania danych z kolekcji, w której każdy element jest parą, która ma klucz sortowania, którego wartość nie musi być unikatowa i skojarzona z nią wartość danych.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<hash_map>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](cpp-standard-library-reference.md)
