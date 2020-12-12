---
description: 'Dowiedz się więcej na temat: __shiftleft128'
title: __shiftleft128
ms.date: 09/02/2019
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: e0e1402660c2ddb6f5993e5186302ff489ed864f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306992"
---
# <a name="__shiftleft128"></a>__shiftleft128

**Specyficzne dla firmy Microsoft**

Przenosi ilość 128-bitową, reprezentowaną jako 2 64-bitowe ilości `LowPart` i `HighPart` , po lewej stronie przez liczbę bitów określoną przez `Shift` , i zwraca wartość o wysokim stopniu 64 bitów wyniku.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __shiftleft128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parametry

*LowPart*\
podczas Niska 64 bitów ilości 128-bitowej do przesunięcia.

*HighPart*\
podczas Wysoka 64 bitów 128-bitowej liczby do przesunięcia.

*Nocn*\
podczas Liczba bitów do przesunięcia.

## <a name="return-value"></a>Wartość zwracana

Wysokie 64 bitów wyniku.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__shiftleft128`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Wartość *przesunięcia* jest zawsze modulo 64, tak więc, na przykład, jeśli wywołasz `__shiftleft128(1, 0, 64)` , funkcja przesunie w lewo bity o niskiej części `0` i zwróci dużą część, `0` a nie `1` jako oczekiwaną w przeciwnym razie.

## <a name="example"></a>Przykład

```C
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__shiftright128](../intrinsics/shiftright128.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
