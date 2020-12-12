---
description: Dowiedz się więcej na temat struktury duration_values
title: duration_values — Struktura
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: 9bf784b0976a06c6d395498084508251d9ebd4bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324478"
---
# <a name="duration_values-structure"></a>duration_values — Struktura

Zawiera określone wartości parametru szablonu [czasu trwania](../standard-library/duration-class.md) `Rep` .

## <a name="syntax"></a>Składnia

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Maksymalny](#max)|Statyczny. Określa górny limit wartości typu `Rep` .|
|[min](#min)|Statyczny. Określa dolny limit dla wartości typu `Rep` .|
|[zer](#zero)|Statyczny. Zwraca wartość `Rep(0)`.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<chrono>

**Przestrzeń nazw:** std:: Chrono

## <a name="duration_valuesmax"></a><a name="max"></a> duration_values:: max

Metoda statyczna zwracająca górną granicę dla wartości typu `Ref` .

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Wartość zwracana

W efekcie zwraca wartość `numeric_limits<Rep>::max()` .

### <a name="remarks"></a>Uwagi

Gdy `Rep` jest typem zdefiniowanym przez użytkownika, zwracana wartość musi być większa niż [duration_values:: zero](#zero).

## <a name="duration_valuesmin"></a><a name="min"></a> duration_values:: min

Metoda statyczna zwracająca dolną granicę dla wartości typu `Ref` .

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Wartość zwracana

W efekcie zwraca wartość `numeric_limits<Rep>::lowest()` .

### <a name="remarks"></a>Uwagi

Gdy `Rep` jest typem zdefiniowanym przez użytkownika, zwracana wartość musi być mniejsza lub równa [duration_values:: zero](#zero).

## <a name="duration_valueszero"></a><a name="zero"></a> duration_values:: zero

Zwraca wartość `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Uwagi

Gdy `Rep` jest typem zdefiniowanym przez użytkownika, zwracana wartość musi reprezentować nieskończoność dodatku.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
