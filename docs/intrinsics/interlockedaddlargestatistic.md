---
description: 'Dowiedz się więcej na temat: _InterlockedAddLargeStatistic'
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 52ca32d0f9b08d638a66923f8f0204eb515b447e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336871"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Specyficzne dla firmy Microsoft**

Wykonuje blokadę, w której pierwszy operand jest wartością 64-bitową.

## <a name="syntax"></a>Składnia

```C
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

### <a name="parameters"></a>Parametry

*Składnik dodawania*\
[in. out] Wskaźnik do pierwszego operandu operacji dodawania. Wartość wskazywana jest zastępowana przez wynik dodania.

*Wartościami*\
podczas Drugi operand; wartość do dodania do pierwszego operandu.

## <a name="return-value"></a>Wartość zwracana

Wartość drugiego operandu.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_InterlockedAddLargeStatistic`Wewnętrzna nie jest niepodzielna, ponieważ jest zaimplementowana jako dwie oddzielne, zablokowane instrukcje. Niepodzielna 64-bitowa odczyt, która występuje w innym wątku podczas wykonywania wewnętrznego, może spowodować odczytanie niespójnej wartości.

`_InterlockedAddLargeStatistic` zachowuje się jako bariera odczytu i zapisu. Aby uzyskać więcej informacji, zobacz [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Konflikty z kompilatorem x86](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
