---
title: sync_per_container — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 378451ac2643d62271fd9e7fa44706a84ee8bb83
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450289"
---
# <a name="syncpercontainer-class"></a>sync_per_container — Klasa

Opisuje [filtr synchronizacji](../standard-library/allocators-header.md) , który zawiera oddzielny obiekt pamięci podręcznej dla każdego obiektu alokatora.

## <a name="syntax"></a>Składnia

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*Pamięć podręczna*|Typ pamięci podręcznej skojarzonej z filtrem synchronizacji. Może to być [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)lub [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[equals](#equals)|Porównuje dwie pamięci podręczne pod kątem równości.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<przypisania >

**Przestrzeń nazw:** stdext

## <a name="equals"></a>sync_per_container:: Equals

Porównuje dwie pamięci podręczne pod kątem równości.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*Pamięć podręczna*|Obiekt pamięci podręcznej filtru synchronizacji.|
|*Inne*|Obiekt pamięci podręcznej, który ma zostać porównany pod kątem równości.|

### <a name="return-value"></a>Wartość zwracana

Funkcja członkowska zawsze zwraca **wartość false**.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz także

[\<allocators>](../standard-library/allocators-header.md)
