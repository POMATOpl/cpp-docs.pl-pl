---
description: Dowiedz się więcej &lt; o &gt; funkcjach losowych
title: '&lt;funkcje losowe &gt;'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 39670fcd9b200a6bd56656bbfa07391fdd0d96be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163343"
---
# <a name="ltrandomgt-functions"></a>&lt;funkcje losowe &gt;

## <a name="generate_canonical"></a><a name="generate_canonical"></a> generate_canonical

Zwraca wartość zmiennoprzecinkową z sekwencji losowej.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parametry

*Liczba rzeczywista*\
Typ całkowity zmiennoprzecinkowy. Aby zapoznać się z możliwymi typami, zobacz [\<random>](../standard-library/random.md) .

*Bitów*\
Liczba bitów losowości do użycia.

*Is*\
Klasa generatora liczb losowych.

*Zbieranie*\
Odwołanie do wystąpienia generatora liczb losowych *generatora* typów.

### <a name="remarks"></a>Uwagi

Funkcja szablonu wielokrotnie wywołuje `operator()` metodę *generacji* i pakuje zwrócone wartości do wartości zmiennoprzecinkowej `x` typu *RealType* do momentu zebrania określonej liczby bitów mantysy w `x` . Określona liczba jest mniejszą liczbą *bitów* (która musi być różna od zera) i pełną liczbą mantysy bitów w *rzeczywistości*. Pierwsze wywołanie dostarcza najniższej kolejności bitów. Funkcja zwraca wartość `x` .
