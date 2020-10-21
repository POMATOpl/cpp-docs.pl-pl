---
title: '&lt;funkcje losowe &gt;'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274593"
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
Odwołanie do wystąpienia generatora liczb losowych *generatora*typów.

### <a name="remarks"></a>Uwagi

Funkcja szablonu wielokrotnie wywołuje `operator()` metodę *generacji* i pakuje zwrócone wartości do wartości zmiennoprzecinkowej `x` typu *RealType* do momentu zebrania określonej liczby bitów mantysy w `x` . Określona liczba jest mniejszą liczbą *bitów* (która musi być różna od zera) i pełną liczbą mantysy bitów w *rzeczywistości*. Pierwsze wywołanie dostarcza najniższej kolejności bitów. Funkcja zwraca wartość `x` .
