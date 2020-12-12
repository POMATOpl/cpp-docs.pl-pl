---
description: Dowiedz się więcej na temat klasy cache_chunklist
title: cache_chunklist — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: 264713ed12727d45928f40f2bc6a790e0e3b1db1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325401"
---
# <a name="cache_chunklist-class"></a>cache_chunklist — Klasa

Definiuje [Alokator bloku](../standard-library/allocators-header.md) , który przydziela i cofa alokacje bloków pamięci o pojedynczym rozmiarze.

## <a name="syntax"></a>Składnia

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Parametry

*Sz*\
Liczba elementów w tablicy, która ma zostać przypisana.

## <a name="remarks"></a>Uwagi

Ten szablon klasy używa **operatora new** do przydzielania fragmentów pamięci nieprzetworzonej, przydzielenia bloków w celu przydzielania magazynu dla bloku pamięci w razie potrzeby; przechowuje cofnięte alokacje bloków pamięci na oddzielnej liście wolnej dla każdego fragmentu i używa **operatora delete** w celu cofnięcia przydziału fragmentu, gdy żaden z jego bloków pamięci nie jest używany.

Każdy blok pamięci zawiera *sz* bajtów użytecznej pamięci i wskaźnik do fragmentu, do którego należy. Każdy fragment zawiera `Nelts` bloki pamięci, trzy wskaźniki, int i dane, które są wymagane przez **operatora new** i **operator delete** .

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[cache_chunklist](#cache_chunklist)|Konstruuje obiekt typu `cache_chunklist` .|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[allocate](#allocate)|Przydziela blok pamięci.|
|[alokowany](#deallocate)|Zwalnia określoną liczbę obiektów z magazynu, zaczynając od określonej pozycji.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<allocators>

**Przestrzeń nazw:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a> cache_chunklist:: Allocate

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a> cache_chunklist:: cache_chunklist

Konstruuje obiekt typu `cache_chunklist` .

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Uwagi

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a> cache_chunklist::d eallocate

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
