---
description: Dowiedz się więcej na temat klasy unchecked_array_iterator
title: unchecked_array_iterator — Klasa
ms.date: 11/04/2016
f1_keywords:
- stdext::unchecked_array_iterator
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
ms.openlocfilehash: 6f2bbe4c31a76101a04e8c5be6a4e0dcf67cf87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132746"
---
# <a name="unchecked_array_iterator-class"></a>unchecked_array_iterator — Klasa

`unchecked_array_iterator`Klasa umożliwia Zawijanie tablicy lub wskaźnika w niesprawdzonym iteratorie. Ta klasa jest używana jako otoka (przy użyciu funkcji [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator) ) dla nieprzetworzonych wskaźników lub tablic jako wskazywany sposób zarządzania ostrzeżeniami o niesprawdzonym wskaźniku zamiast globalnie wyciszania tych ostrzeżeń. Jeśli to możliwe, Preferuj sprawdzoną wersję tej klasy, [checked_array_iterator](../standard-library/checked-array-iterator-class.md).

> [!NOTE]
> Ta klasa jest rozszerzeniem firmy Microsoft biblioteki standardowej języka C++. Kod zaimplementowany przy użyciu tej funkcji nie jest przenośny do standardowych środowisk kompilacji C++, które nie obsługują tego rozszerzenia Microsoft.

## <a name="syntax"></a>Składnia

```cpp
template <class Iterator>
class unchecked_array_iterator;
```

## <a name="remarks"></a>Uwagi

Ta klasa jest zdefiniowana w przestrzeni nazw [stdext](../standard-library/stdext-namespace.md) .

Jest to niesprawdzona wersja [klasy checked_array_iterator](../standard-library/checked-array-iterator-class.md) i obsługuje wszystkie te same przeciążenia i elementy członkowskie. Aby uzyskać więcej informacji na temat funkcji sprawdzonego iteratora z przykładami kodu, zobacz [sprawdzone Iteratory](../standard-library/checked-iterators.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iterator>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[\<iterator>](../standard-library/iterator.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
