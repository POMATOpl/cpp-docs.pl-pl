---
description: Dowiedz się więcej na temat klasy allocator_unbounded
title: allocator_unbounded — Klasa
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 6d046aa08ddd366c7e7009d1d93c36a365d98170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163551"
---
# <a name="allocator_unbounded-class"></a>allocator_unbounded — Klasa

Opisuje obiekt, który zarządza alokacją i zwalnianiem magazynu dla *obiektów typu Type przy użyciu* pamięci podręcznej typu [cache_freelist](cache-freelist-class.md) o długości zarządzanej przez [max_unbounded](max-unbounded-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>Parametry

*Wprowadź*\
Typ elementów przyznanych przez alokatora.

## <a name="remarks"></a>Uwagi

Makro [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) przekazuje tę klasę jako parametr *name* w następującej instrukcji: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<allocators>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[\<allocators>](allocators-header.md)
