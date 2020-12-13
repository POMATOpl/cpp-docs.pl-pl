---
description: 'Dowiedz się więcej na temat: _div64'
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 4c9c8f02f7092c12d5734f96346897e2eca9898a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337075"
---
# <a name="_div64"></a>_div64

`_div64`Wewnętrznie dzieli 64-bitową liczbę całkowitą przez 32-bitową liczbę całkowitą. Wartość zwracana utrzymuje iloraz, a wewnętrzna Zwraca resztę za pomocą parametru wskaźnika. `_div64` jest **specyficzny dla firmy Microsoft**.

## <a name="syntax"></a>Składnia

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Parametry

*płacone* \
podczas 64-bitowa liczba całkowita do podzielenia.

*dzielnik* \
podczas 32-bitowa liczba całkowita do podzielenia przez.

*pozostałej części* \
określoną 32-bitowe całkowite bity reszty.

## <a name="return-value"></a>Wartość zwracana

32 bitów ilorazu.

## <a name="remarks"></a>Uwagi

`_div64`Wewnętrznie dzieli *dzielną* przez *dzielnik*. Przechowuje resztę z 32-bitowej liczby całkowitej wskazywanej przez *resztę* i zwraca 32 bitów ilorazu.

Funkcja `_div64` wewnętrzna jest dostępna od wersji Visual Studio 2019 RTM.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|Nagłówek|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>Zobacz też

[_udiv64](udiv64.md) \
[Funkcje wewnętrzne kompilatora](compiler-intrinsics.md)
