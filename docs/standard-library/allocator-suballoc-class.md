---
title: allocator_suballoc — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
ms.openlocfilehash: 9136a2ce744e19754b3a660e7bc9c15f05babbbf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610656"
---
# <a name="allocatorsuballoc-class"></a>allocator_suballoc — Klasa

Opisuje obiekt, który zarządza alokacją pamięci i zwalnianiem dla obiektów typu *typu* używanie pamięci podręcznej typu [cache_suballoc](../standard-library/cache-suballoc-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>Parametry

|Parametr|Opis|
|---------------|-----------------|
|*Typ*|Typ elementów przydzielonej przez alokator.|

## <a name="remarks"></a>Uwagi

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) — makro przekazuje tę klasę jako *nazwa* parametru w następującej instrukcji: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<buforów >

**Namespace:** stdext

## <a name="see-also"></a>Zobacz także

[\<allocators — >](../standard-library/allocators-header.md)<br/>
