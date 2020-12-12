---
description: 'Dowiedz się więcej na temat: _WriteBarrier'
title: _WriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: 7fe78eaa30e7971853ff9d73d7142b8eeddb679f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313141"
---
# <a name="_writebarrier"></a>_WriteBarrier

**Specyficzne dla firmy Microsoft**

Ogranicza optymalizacje kompilatora, które mogą zmienić kolejność operacji dostępu do pamięci w punkcie wywołania.

> [!CAUTION]
> Elementy `_ReadBarrier` `_WriteBarrier` wewnętrzne, i i `_ReadWriteBarrier` `MemoryBarrier` makro są przestarzałe i nie powinny być używane. W przypadku komunikacji między wątkami należy używać takich mechanizmów jak [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) i [std: \<T> :](../standard-library/atomic.md)informowanie, które są zdefiniowane w [standardowej bibliotece języka C++](../standard-library/cpp-standard-library-reference.md). Aby uzyskać dostęp do sprzętu, użyj opcji kompilatora [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) wraz ze słowem kluczowym [volatile](../cpp/volatile-cpp.md) .

## <a name="syntax"></a>Składnia

```C
void _WriteBarrier(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_WriteBarrier`Wewnętrzna ogranicza optymalizacje kompilatora, które mogą usuwać lub zmienić kolejność operacji dostępu do pamięci w punkcie wywołania.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
