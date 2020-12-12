---
description: Dowiedz się więcej na temat klasy allocator_fixed_size
title: allocator_fixed_size — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: b4b3452a611734dd2731bdb9c43e4bf7a7ce6744
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163603"
---
# <a name="allocator_fixed_size-class"></a>allocator_fixed_size — Klasa

Opisuje obiekt, który zarządza alokacją i zwalnianiem magazynu dla *obiektów typu Type przy użyciu* pamięci podręcznej typu [cache_freelist](cache-freelist-class.md) o długości zarządzanej przez [max_fixed_size](max-fixed-size-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>Parametry

*Wprowadź*\
Typ elementów przyznanych przez alokatora.

## <a name="remarks"></a>Uwagi

Makro [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) przekazuje tę klasę jako parametr *name* w następującej instrukcji: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<allocators>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[\<allocators>](allocators-header.md)
