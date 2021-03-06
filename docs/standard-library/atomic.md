---
title: '&lt;atomic&gt;'
description: Opisuje typy i funkcje dostępne w postaci niepodzielnego nagłówka standardowej biblioteki języka C++.
ms.date: 12/06/2019
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
ms.openlocfilehash: 3c5f732dbda701eb7744b1b25a9a8e7426f7a3e2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203905"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Definiuje klasy i szablony klas, które mają być używane do tworzenia typów, które obsługują operacje niepodzielne.

## <a name="syntax"></a>Składnia

```cpp
#include <atomic>
```

## <a name="remarks"></a>Uwagi

> [!NOTE]
> W kodzie, który jest kompilowany za pomocą [/CLR: Pure](../build/reference/clr-common-language-runtime-compilation.md), ten nagłówek jest zablokowany. Oba **/CLR: Pure** i **/CLR: Safe** są przestarzałe w programie Visual Studio 2017 i nowszych wersjach.

Operacja niepodzielna ma dwie właściwości klucza, które ułatwiają poprawne manipulowanie obiektem bez użycia blokad muteksów.

- Ponieważ operacja niepodzielna jest nierozdzielna, druga niepodzielna operacja na tym samym obiekcie z innego wątku może uzyskać stan obiektu tylko przed pierwszą operacją niepodzielną.

- W oparciu o jego [memory_order](../standard-library/atomic-enums.md#memory_order_enum) , niepodzielna operacja ustala wymagania dotyczące porządkowania dla widoczności efektów innych operacji niepodzielnych w tym samym wątku. W związku z tym wstrzymuje optymalizacje kompilatora, które naruszają wymagania dotyczące porządkowania.

Na niektórych platformach może nie być możliwe wydajne Implementowanie operacji niepodzielnych dla niektórych typów bez używania `mutex` blokad. Typ niepodzielny jest *zablokowany* , jeśli żadna niepodzielna operacja na tym typie nie używa blokad.

**C++ 11**: w obsłudze sygnałów, można wykonywać operacje niepodzielne na obiekcie, `obj` Jeśli `obj.is_lock_free()` lub `atomic_is_lock_free(x)` są spełnione.

Klasa [atomic_flag](../standard-library/atomic-flag-structure.md) zapewnia minimalny typ niepodzielny, który posiada **`bool`** flagę. Jego operacje są zawsze odblokowywane bezpłatnie.

Szablon klasy `atomic<T>` Przechowuje obiekt typu argumentu `T` i zapewnia dostęp do tej wartości. Można utworzyć wystąpienie go przy użyciu dowolnego typu, który można skopiować za pomocą [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) i przetestowano pod kątem równości przy użyciu [funkcji memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md). W szczególności można użyć go z typami zdefiniowanymi przez użytkownika, które spełniają te wymagania, a w wielu przypadkach z typami zmiennoprzecinkowymi.

Szablon zawiera również zestaw specjalizacji dla typów całkowitych i częściowej specjalizacji wskaźników. Specjalizacje te zapewniają dodatkowe operacje, które nie są dostępne za pomocą szablonu podstawowego.

## <a name="pointer-specializations"></a>Specjalizacje wskaźnika

`atomic<T *>`Częściowe specjalizacje stosują się do wszystkich typów wskaźnika. Udostępniają one metody arytmetyczne wskaźnika.

## <a name="integral-specializations"></a>Niezintegrowane specjalizacje

`atomic<integral>`Specjalizacje stosują się do wszystkich typów całkowitych. Zapewniają one dodatkowe operacje, które nie są dostępne za pomocą szablonu podstawowego.

Każdy `atomic<integral>` Typ ma odpowiednie makro, którego można użyć w `if directive` celu określenia czasu kompilacji, niezależnie od tego, czy operacje na tym typie są wolne od blokady. Jeśli wartość makra jest równa zero, operacje na typie nie są wolne od blokady. Jeśli wartość wynosi 1, operacje mogą być wolne od blokady i wymagane jest sprawdzenie środowiska uruchomieniowego. Jeśli wartość jest równa 2, operacje są wolne od blokady. Za pomocą funkcji można `atomic_is_lock_free` określić, czy w czasie wykonywania operacje na typie są wolne od blokady.

Dla każdego z typów całkowitych istnieje odpowiedni nazwany typ niepodzielny, który zarządza obiektem tego typu całkowitego. Każdy `atomic_integral` Typ ma ten sam zestaw funkcji składowych, co odpowiadające mu wystąpienie `atomic<T>` i może być przesłany do którejkolwiek z nienależących do nich funkcji niepodzielnych.

|`atomic_integral`Wprowadź|Typ całkowity|`atomic_is_lock_free`Makro|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**`char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**`signed char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**`unsigned char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|**`char16_t`**|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|**`char32_t`**|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**`wchar_t`**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**`short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**`unsigned short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**`int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**`unsigned int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**`long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**`unsigned long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**`long long`**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**`unsigned long long`**|ATOMIC_LLONG_LOCK_FREE|

Nazwy typedef istnieją dla specjalizacji szablonu niepodzielnego dla niektórych typów, które są zdefiniowane w nagłówku \<inttypes.h> .

|Typ niepodzielny|Nazwa typedef|
|-----------------|------------------|
|`atomic_int8_t`|`atomic<int8_t>`|
|`atomic_uint8_t`|`atomic<uint8_t>`|
|`atomic_int16_t`|`atomic<int16_t>`|
|`atomic_uint16_t`|`atomic<uint16_t>`|
|`atomic_int32_t`|`atomic<int32_t>`|
|`atomic_uint32_t`|`atomic<uint32_t>`|
|`atomic_int64_t`|`atomic<int64_t>`|
|`atomic_uint64_t`|`atomic<uint64_t>`|
|`atomic_int_least8_t`|`atomic<int_least8_t>`|
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|
|`atomic_int_least16_t`|`atomic<int_least16_t>`|
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|
|`atomic_int_least32_t`|`atomic<int_least32_t>`|
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|
|`atomic_int_least64_t`|`atomic<int_least64_t>`|
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|
|`atomic_intptr_t`|`atomic<intptr_t>`|
|`atomic_uintptr_t`|`atomic<uintptr_t>`|
|`atomic_size_t`|`atomic<size_t>`|
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|
|`atomic_intmax_t`|`atomic<intmax_t>`|
|`atomic_uintmax_t`|`atomic<uintmax_t>`|

## <a name="structs"></a>Struktury

|Nazwa|Opis|
|----------|-----------------|
|[atomic — Struktura](../standard-library/atomic-structure.md)|Opisuje obiekt, który wykonuje operacje niepodzielne na przechowywanej wartości.|
|[atomic_flag — Struktura](../standard-library/atomic-flag-structure.md)|Opisuje obiekt, który niepodzielnie ustawia i czyści **`bool`** flagę.|

## <a name="enums"></a>Wyliczenia

|Nazwa|Opis|
|----------|-----------------|
|[memory_order Wyliczenie](../standard-library/atomic-enums.md#memory_order_enum)|Dostarcza symboliczne nazwy dla operacji synchronizacji w lokalizacjach pamięci. Te operacje wpływają na sposób, w jaki przypisania w jednym wątku stają się widoczne w innym.|

## <a name="functions"></a>Funkcje

Na poniższej liście funkcje, które nie kończą się w programie, `_explicit` mają semantykę odpowiadającą `_explicit` , z tą różnicą, że mają niejawne argumenty [memory_order](../standard-library/atomic-enums.md#memory_order_enum) `memory_order_seq_cst` .

|Nazwa|Opis|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|Wykonuje *porównanie atomowe i wymianę* operacji.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|Wykonuje *porównanie atomowe i wymianę* operacji.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|Wykonuje *słabą, niepodzielną operację porównania i wymiany* .|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|Wykonuje *słabą, niepodzielną operację porównania i wymiany* .|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Zastępuje przechowywaną wartość.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Zastępuje przechowywaną wartość.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Dodaje określoną wartość do istniejącej wartości przechowywanej.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Dodaje określoną wartość do istniejącej wartości przechowywanej.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Wykonuje wartość bitową `and` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Wykonuje wartość bitową `and` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Wykonuje wartość bitową `or` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Wykonuje wartość bitową `or` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Odejmuje określoną wartość od istniejącej przechowywanej wartości.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Odejmuje określoną wartość od istniejącej przechowywanej wartości.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Wykonuje wartość bitową `exclusive or` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Wykonuje wartość bitową `exclusive or` dla określonej wartości i istniejącej wartości przechowywanej.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Ustawia flagę w `atomic_flag` obiekcie na **`false`** .|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Ustawia flagę w `atomic_flag` obiekcie na **`false`** .|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Ustawia flagę w `atomic_flag` obiekcie na **`true`** .|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Ustawia flagę w `atomic_flag` obiekcie na **`true`** .|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|Ustawia wartość przechowywaną w `atomic` obiekcie.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Określa, czy operacje niepodzielne na określonym obiekcie są wolne od blokady.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Niepodzielnie Pobiera wartość.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Niepodzielnie Pobiera wartość.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Działa jako *ogrodzenie* ustanawiające wymagania dotyczące porządkowania pamięci między ogrodzeniami w wątku wywołującym, które ma programy obsługi sygnałów wykonywane w tym samym wątku.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Niepodzielne przechowuje wartość.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Niepodzielne przechowuje wartość.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|Działa jako *ogrodzenie* ustanawiające wymagania dotyczące porządkowania pamięci w odniesieniu do innych ogrodzeniów.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Dzieli możliwy łańcuch zależności.|

## <a name="see-also"></a>Zobacz także

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
