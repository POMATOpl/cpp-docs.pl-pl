---
description: Dowiedz się więcej na temat struktury input_iterator_tag
title: input_iterator_tag — Struktura
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 92bd110af71aecfa632b8e739126698eba457019
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231709"
---
# <a name="input_iterator_tag-struct"></a>input_iterator_tag — Struktura

Klasa udostępniająca typ zwracany dla `iterator_category` funkcji, która reprezentuje iterator wejściowy.

## <a name="syntax"></a>Składnia

Struktura input_iterator_tag {} ;

## <a name="remarks"></a>Uwagi

Klasy tagów kategorii są używane jako Tagi kompilacji do wyboru algorytmów. Funkcja szablonu musi znaleźć najbardziej specyficzną kategorię jego argumentu iteratora, aby można było używać najbardziej wydajnego algorytmu w czasie kompilacji. Dla każdego iteratora typu `Iterator` , `iterator_traits` <  `Iterator` >  **:: iterator_category** musi być zdefiniowana jako najbardziej konkretny tag kategorii, który opisuje zachowanie iteratora.

Typ jest taki sam jak **iterator** \< **Iter**> **:: iterator_category** , gdy `Iter` opisuje obiekt, który może być używany jako iterator wejściowy.

## <a name="example"></a>Przykład

Zapoznaj się z tematem [iterator_traits](../standard-library/iterator-traits-struct.md) lub [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) , aby zapoznać się z przykładem użycia usługi `iterator_tag` s.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iterator>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
