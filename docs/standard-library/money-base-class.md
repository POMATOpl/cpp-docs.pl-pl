---
description: Dowiedz się więcej na temat klasy money_base
title: money_base — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 295984cfed4d6fdd47c772e29765c1484f52d32a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230474"
---
# <a name="money_base-class"></a>money_base — Klasa

Klasa opisuje Wyliczenie i strukturę wspólną dla wszystkich specjalizacji szablonu klasy [moneypunct](../standard-library/moneypunct-class.md).

## <a name="syntax"></a>Składnia

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Uwagi

Wyliczenie `part` opisuje możliwe wartości w elementach pola tablicy we wzorcu struktury. Wartości `part` są:

- `none` Aby dopasować zero lub więcej spacji lub wygenerować Nothing.

- `sign` Aby dopasować lub wygenerować znak dodatni lub ujemny.

- `space` Aby dopasować zero lub więcej spacji lub wygenerować spację.

- `symbol` Aby dopasować lub wygenerować symbol waluty.

- `value` Aby dopasować lub wygenerować wartość pieniężną.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
