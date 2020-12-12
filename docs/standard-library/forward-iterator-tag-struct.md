---
description: Dowiedz się więcej na temat struktury forward_iterator_tag
title: forward_iterator_tag — Struktura
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 9b8b5ea7ff4e7d68c14c892d4ba6ef96f275b7da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324299"
---
# <a name="forward_iterator_tag-struct"></a>forward_iterator_tag — Struktura

Klasa udostępniająca typ zwracany dla funkcji **iterator_category** , która reprezentuje iterator do przodu.

## <a name="syntax"></a>Składnia

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Uwagi

Klasy tagów kategorii są używane jako Tagi kompilacji do wyboru algorytmów. Funkcja szablonu musi dowiedzieć się, co jest najbardziej konkretną kategorią argumentu iteratora, tak aby można było użyć najbardziej wydajnego algorytmu w czasie kompilacji. Dla każdego iteratora typu `Iterator` , `iterator_traits` <  `Iterator` >  **:: iterator_category** musi być zdefiniowana jako najbardziej konkretny tag kategorii, który opisuje zachowanie iteratora.

Typ jest taki sam jak **iterator** \< **Iter**> **:: iterator_category** , gdy **ITER** opisuje obiekt, który może być używany jako iterator do przodu.

## <a name="example"></a>Przykład

Zobacz [iterator_traits](../standard-library/iterator-traits-struct.md) lub [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) , aby zapoznać się z przykładem użycia **iterator_tag** s.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iterator>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Struktura input_iterator_tag](../standard-library/input-iterator-tag-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
