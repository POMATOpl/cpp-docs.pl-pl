---
description: 'Dowiedz się więcej na temat: _ReadWriteBarrier'
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: ff537d4f3b117b52ba567bf0d130e51d0062965f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294122"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Specyficzne dla firmy Microsoft**

Ogranicza optymalizacje kompilatora, które mogą zmienić kolejność dostępu do pamięci w punkcie wywołania.

> [!CAUTION]
> Elementy `_ReadBarrier` `_WriteBarrier` wewnętrzne, i i `_ReadWriteBarrier` `MemoryBarrier` makro są przestarzałe i nie powinny być używane. W przypadku komunikacji między wątkami należy używać takich mechanizmów jak [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) i [std: \<T> :](../standard-library/atomic.md)informowanie, które są zdefiniowane w [standardowej bibliotece języka C++](../standard-library/cpp-standard-library-reference.md). Aby uzyskać dostęp do sprzętu, użyj opcji kompilatora [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) wraz ze słowem kluczowym [volatile](../cpp/volatile-cpp.md) .

## <a name="syntax"></a>Składnia

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_ReadWriteBarrier`Wewnętrzna ogranicza optymalizacje kompilatora, które mogą usuwać lub zmienić kolejność dostępu do pamięci w punkcie wywołania.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_WriteBarrier](../intrinsics/writebarrier.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
