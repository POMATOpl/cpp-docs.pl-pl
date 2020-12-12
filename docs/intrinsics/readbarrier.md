---
description: 'Dowiedz się więcej na temat: _ReadBarrier'
title: _ReadBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadBarrier
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
ms.openlocfilehash: 94ade7c8f602cf279ac75a5f0a56387c344d0fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257498"
---
# <a name="_readbarrier"></a>_ReadBarrier

**Specyficzne dla firmy Microsoft**

Ogranicza optymalizacje kompilatora, które mogą zmienić kolejność operacji dostępu do pamięci w punkcie wywołania.

> [!CAUTION]
> Elementy `_ReadBarrier` `_WriteBarrier` wewnętrzne, i i `_ReadWriteBarrier` `MemoryBarrier` makro są przestarzałe i nie powinny być używane. W przypadku komunikacji między wątkami należy używać takich mechanizmów jak [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) i [std: \<T> :](../standard-library/atomic.md) informowanie, które są zdefiniowane w [standardowej bibliotece języka C++](../standard-library/cpp-standard-library-reference.md). Aby uzyskać dostęp do sprzętu, użyj opcji kompilatora [/volatile: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) wraz ze słowem kluczowym [volatile](../cpp/volatile-cpp.md) .

## <a name="syntax"></a>Składnia

```C
void _ReadBarrier(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_ReadBarrier`Wewnętrzna ogranicza optymalizacje kompilatora, które mogą usuwać lub zmienić kolejność operacji dostępu do pamięci w punkcie wywołania.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
