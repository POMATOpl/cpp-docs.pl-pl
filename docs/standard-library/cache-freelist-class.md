---
description: Dowiedz się więcej na temat klasy cache_freelist
title: cache_freelist — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: 9d5b3da272cff39b0c9d7d69df2c744d6952cd03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325385"
---
# <a name="cache_freelist-class"></a>cache_freelist — Klasa

Definiuje [Alokator bloku](../standard-library/allocators-header.md) , który przydziela i cofa alokacje bloków pamięci o pojedynczym rozmiarze.

## <a name="syntax"></a>Składnia

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parametry

*Sz*\
Liczba elementów w tablicy, która ma zostać przypisana.

*Maksymalny*\
Maksymalna Klasa reprezentująca maksymalny rozmiar listy bezpłatnej. Może to być [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md)lub [max_variable_size](../standard-library/max-variable-size-class.md).

## <a name="remarks"></a>Uwagi

Szablon klasy cache_freelist przechowuje bezpłatną listę bloków pamięci o rozmiarze *sz*. Gdy lista bezpłatnych jest pełna, użyje **operatora delete** w celu cofnięcia alokacji bloków pamięci. Gdy lista bezpłatnych jest pusta, używa **operatora new** w celu przydzielenia nowych bloków pamięci. Maksymalny rozmiar bezpłatnej listy jest określany przez maksymalną klasę klasy przekazaną w parametrze *Max* .

Każdy blok pamięci zawiera *sz* bajtów użytecznej pamięci oraz dane, które **operator new** i **operator delete** wymagają.

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[cache_freelist](#cache_freelist)|Konstruuje obiekt typu `cache_freelist` .|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[allocate](#allocate)|Przydziela blok pamięci.|
|[alokowany](#deallocate)|Zwalnia określoną liczbę obiektów z magazynu, zaczynając od określonej pozycji.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<allocators>

**Przestrzeń nazw:** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a> cache_freelist:: Allocate

Przydziela blok pamięci.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametry

*liczbą*\
Liczba elementów w tablicy, która ma zostać przypisana.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do przydzielony obiekt.

### <a name="remarks"></a>Uwagi

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a> cache_freelist:: cache_freelist

Konstruuje obiekt typu `cache_freelist` .

```cpp
cache_freelist();
```

### <a name="remarks"></a>Uwagi

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a> cache_freelist::d eallocate

Zwalnia określoną liczbę obiektów z magazynu, zaczynając od określonej pozycji.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametry

*PTR*\
Wskaźnik do pierwszego obiektu do cofnięcia przydziału z magazynu.

*liczbą*\
Liczba obiektów do cofnięcia przydziału z magazynu.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[\<allocators>](../standard-library/allocators-header.md)
