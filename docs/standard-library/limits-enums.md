---
description: 'Dowiedz się więcej o: &lt; limity &gt; wyliczeń'
title: '&lt;limity typów &gt; wyliczeniowych'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 115122a4901298018df8809be56a7fc69249d700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312868"
---
# <a name="ltlimitsgt-enums"></a>&lt;limity typów &gt; wyliczeniowych

## <a name="float_denorm_style"></a><a name="float_denorm_style"></a> float_denorm_style

Wyliczenie opisuje różne metody, które można wybrać do reprezentowania nieznormalizowanej wartości zmiennoprzecinkowej — jeden za mały, aby reprezentować jako znormalizowaną wartość:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Wartość zwracana

Wyliczenie zwraca:

- `denorm_indeterminate` Jeśli nie można określić obecności lub braku nieznormalizowanych formularzy w czasie tłumaczenia.

- `denorm_absent` Jeśli nieznormalizowane formularze są nieobecne.

- `denorm_present` Jeśli istnieją nieznormalizowane formularze.

### <a name="example"></a>Przykład

Zobacz [numeric_limits:: has_denorm](../standard-library/numeric-limits-class.md#has_denorm) , aby zapoznać się z przykładem, w którym można uzyskać dostęp do wartości tego wyliczenia.

## <a name="float_round_style"></a><a name="float_round_style"></a> float_round_style

Wyliczenie opisuje różne metody, które można wybrać, aby zaokrąglić wartość zmiennoprzecinkową do wartości całkowitej.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Wartość zwracana

Wyliczenie zwraca:

- `round_indeterminate` Jeśli nie można ustalić metody zaokrąglania.

- `round_toward_zero` Jeśli wartość jest zaokrąglana w kierunku zera.

- `round_to_nearest` Jeśli Zaokrąglij do najbliższej liczby całkowitej.

- `round_toward_infinity` Jeśli wartość jest zaokrąglana w kierunku od zera.

- `round_toward_neg_infinity` Jeśli Zaokrąglij do bardziej ujemną liczbę całkowitą.

### <a name="example"></a>Przykład

Zobacz [numeric_limits:: round_style](../standard-library/numeric-limits-class.md#round_style) , aby zapoznać się z przykładem, w którym można uzyskać dostęp do wartości tego wyliczenia.
