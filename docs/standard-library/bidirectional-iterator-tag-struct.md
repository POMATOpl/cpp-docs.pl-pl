---
description: Dowiedz się więcej na temat struktury bidirectional_iterator_tag
title: bidirectional_iterator_tag — Struktura
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: db8de79c0fa5f9c748d453fcba7443351dcf217d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325562"
---
# <a name="bidirectional_iterator_tag-struct"></a>bidirectional_iterator_tag — Struktura

Klasa udostępniająca typ zwracany dla `iterator_category` funkcji, która reprezentuje iterator dwukierunkowy.

## <a name="syntax"></a>Składnia

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Uwagi

Klasy tagów kategorii są używane jako Tagi kompilacji do wyboru algorytmów. Funkcja szablonu musi znaleźć najbardziej specyficzną kategorię jego argumentu iteratora, tak aby można było użyć najbardziej wydajnego algorytmu w czasie kompilacji. Dla każdego iteratora typu `Iterator` , `iterator_traits` <  `Iterator`>:: **iterator_category** musi być zdefiniowana jako najbardziej konkretny tag kategorii, który opisuje zachowanie iteratora.

Typ jest taki sam jak **iterator** \< **Iter**> :: **iterator_category** , gdy `Iter` opisuje obiekt, który może być używany jako iterator dwukierunkowy.

## <a name="example"></a>Przykład

Zobacz [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) , aby zapoznać się z przykładem sposobu korzystania z programu `bidirectional_iterator_tag` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iterator>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Struktura forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
