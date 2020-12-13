---
description: Dowiedz się więcej na temat struktury atomic_flag
title: atomic_flag — Struktura
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: f78e3fa8521d230cc119dd7c464653cb6e123733
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149503"
---
# <a name="atomic_flag-structure"></a>atomic_flag — Struktura

Opisuje obiekt, który niepodzielnie ustawia i czyści **`bool`** flagę. Operacje na flagach niepodzielnych są zawsze zablokowane.

## <a name="syntax"></a>Składnia

```cpp
struct atomic_flag;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Wyczyść](#clear)|Ustawia wartość przechowywanej flagi na **`false`** .|
|[test_and_set](#test_and_set)|Ustawia wartość przechowywanej flagi na **`true`** i zwraca początkową wartością flagi.|

## <a name="remarks"></a>Uwagi

`atomic_flag` obiekty mogą być przesyłane do funkcji nienależących do elementu członkowskiego [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)i [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit). Można je zainicjować przy użyciu wartości `ATOMIC_FLAG_INIT` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<atomic>

**Przestrzeń nazw:** std

## <a name="atomic_flagclear"></a><a name="clear"></a> atomic_flag:: Clear

Ustawia **`bool`** flagę przechowywaną w **`*this`** do **`false`** , w ramach określonych ograniczeń [memory_order](../standard-library/atomic-enums.md#memory_order_enum) .

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametry

*Porządek*\
[Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a> atomic_flag:: test_and_set

Ustawia **`bool`** flagę przechowywaną w **`*this`** do **`true`** , w ramach określonych ograniczeń [memory_order](../standard-library/atomic-enums.md#memory_order_enum) .

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parametry

*Porządek*\
[Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Wartość zwracana

Początkowa wartość flagi, która jest przechowywana w **`*this`** .

## <a name="see-also"></a>Zobacz też

[\<atomic>](../standard-library/atomic.md)
