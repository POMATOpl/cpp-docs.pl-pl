---
description: Dowiedz się więcej na temat klasy discard_block_engine
title: discard_block_engine — Klasa
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 0879dacac70afc78a9c77314ce5042580c6cbb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324519"
---
# <a name="discard_block_engine-class"></a>discard_block_engine — Klasa

Generuje losową sekwencję przez odrzucenie wartości zwracanych przez aparat podstawowy.

## <a name="syntax"></a>Składnia

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parametry

*Wyszukiwarce*\
Typ aparatu podstawowego.

*St*\
**Rozmiar bloku**. Liczba wartości w każdym bloku.

*®*\
**Używany blok**. Liczba wartości w każdym używanym bloku. Pozostałe są odrzucane ( `P`  -  `R` ). **Warunek wstępny**: `0 < R ≤ P`

## <a name="members"></a>Elementy członkowskie

`discard_block_engine::discard_block_engine`\
`discard_block_engine::base`\
`discard_block_engine::base_type`\
`discard_block_engine::discard`\
`discard_block_engine::operator()`\
`discard_block_engine::seed`

Aby uzyskać więcej informacji na temat elementów członkowskich silnika, zobacz [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Uwagi

Ten szablon klasy zawiera opis adaptera, który tworzy wartości przez odrzucenie niektórych wartości zwracanych przez aparat podstawowy.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<random>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<random>](../standard-library/random.md)
