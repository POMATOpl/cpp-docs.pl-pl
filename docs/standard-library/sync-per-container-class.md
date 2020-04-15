---
title: sync_per_container — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 2c60911b5469cbf74944c9f63af44f2351790280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376554"
---
# <a name="sync_per_container-class"></a>sync_per_container — Klasa

W tym artykule opisano [filtr synchronizacji,](../standard-library/allocators-header.md) który udostępnia oddzielny obiekt pamięci podręcznej dla każdego obiektu alokatora.

## <a name="syntax"></a>Składnia

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*Pamięć podręczna*|Typ pamięci podręcznej skojarzonej z filtrem synchronizacji. Może to być [cache_chunklist,](../standard-library/cache-chunklist-class.md) [cache_freelist](../standard-library/cache-freelist-class.md)lub [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowce|Opis|
|-|-|
|[equals](#equals)|Porównuje dwie pamięci podręczne dla równości.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<alokatory>

**Obszar nazw:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container::równa się

Porównuje dwie pamięci podręczne dla równości.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*Pamięć podręczna*|Obiekt pamięci podręcznej filtru synchronizacji.|
|*Inne*|Obiekt pamięci podręcznej do porównania dla równości.|

### <a name="return-value"></a>Wartość zwracana

Funkcja elementu członkowskiego zawsze zwraca **wartość false**.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[\<>alokatorów](../standard-library/allocators-header.md)
