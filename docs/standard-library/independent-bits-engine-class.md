---
description: Dowiedz się więcej na temat klasy independent_bits_engine
title: independent_bits_engine — Klasa
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: 8da68469c266fae1f9c966b586ea66973d871dc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231689"
---
# <a name="independent_bits_engine-class"></a>independent_bits_engine — Klasa

Generuje losową sekwencję liczb z określoną liczbą bitów przez przepakowywanie bitów z wartości zwracanych przez aparat podstawowy.

## <a name="syntax"></a>Składnia

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parametry

*Wyszukiwarce*\
Typ aparatu podstawowego.

*K*\
**Rozmiar wyrazu**. Rozmiar w bitach dla każdej wygenerowanej liczby. **Warunek wstępny**: `0 < W ≤ numeric_limits<UIntType>::digits`

*UInttype*\
Typ wyniku bez znaku liczby całkowitej. Aby zapoznać się z możliwymi typami, zobacz [\<random>](../standard-library/random.md) .

## <a name="members"></a>Elementy członkowskie

`independent_bits_engine::independent_bits_engine`\
`independent_bits_engine::base`\
`independent_bits_engine::base_type`\
`independent_bits_engine::discard`\
`independent_bits_engine::operator()`\
`independent_bits_engine::seed`

Aby uzyskać więcej informacji na temat elementów członkowskich silnika, zobacz [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Uwagi

Ten szablon klasy zawiera opis *adaptera* , który tworzy wartości poprzez przepakowywanie bitów z wartości zwracanych przez aparat podstawowy, co spowodowało *wartości w bitach*.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<random>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<random>](../standard-library/random.md)
