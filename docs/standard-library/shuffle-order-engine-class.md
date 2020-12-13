---
description: Dowiedz się więcej na temat klasy shuffle_order_engine
title: shuffle_order_engine — Klasa
ms.date: 11/04/2016
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
ms.openlocfilehash: 3be8438ac0809d697d081d998450bde09d1d583e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154022"
---
# <a name="shuffle_order_engine-class"></a>shuffle_order_engine — Klasa

Generuje losową sekwencję przez zmianę kolejności wartości zwracanych z aparatu podstawowego.

## <a name="syntax"></a>Składnia

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametry

*Wyszukiwarce*\
Typ aparatu podstawowego.

*K*\
**Rozmiar tabeli**. Liczba elementów w buforze (tabela). **Warunek wstępny**: `0 < K`

## <a name="members"></a>Elementy członkowskie

`shuffle_order_engine::shuffle_order_engine`\
`shuffle_order_engine::base`\
`shuffle_order_engine::base_type`\
`shuffle_order_engine::discard`\
`shuffle_order_engine::operator()`\
`shuffle_order_engine::seed`

Aby uzyskać więcej informacji na temat elementów członkowskich silnika, zobacz [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Uwagi

Ten szablon klasy zawiera opis *adaptera* , który tworzy wartości przez zmianę kolejności wartości zwracanych przez silnik podstawowy. Każdy Konstruktor wypełnia wewnętrzną tabelę o wartościach *K* zwracanych przez silnik podstawowy i wybiera losowo element z tabeli, gdy jest wymagana wartość.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<random>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<random>](../standard-library/random.md)
