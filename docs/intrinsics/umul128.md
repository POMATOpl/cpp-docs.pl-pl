---
description: 'Dowiedz się więcej na temat: _umul128'
title: _umul128
ms.date: 09/02/2019
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: 7fd126b169bd01fc4d51d186879e019f8d86f008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333601"
---
# <a name="_umul128"></a>_umul128

**Specyficzne dla firmy Microsoft**

Mnoży 2 64-bitowe liczby całkowite bez znaku przekazane jako pierwsze dwa argumenty i umieszczają o wysokim stopniu 64 bitów produktu w 64-bitową liczbę całkowitą bez znaku wskazywanym przez `HighProduct` i zwraca 64 niską liczbę bitów produktu.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 _umul128(
   unsigned __int64 Multiplier,
   unsigned __int64 Multiplicand,
   unsigned __int64 *HighProduct
);
```

### <a name="parameters"></a>Parametry

*Mnożnik*\
podczas Pierwszy 64-bitową liczbę całkowitą do pomnożenia.

*Multiplicand*\
podczas Druga 64-bitowa liczba całkowita do pomnożenia.

*HighProduct*\
określoną Wysoki 64 bitów produktu.

## <a name="return-value"></a>Wartość zwracana

Niska 64 bitów produktu.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|Nagłówek|
|---------------|------------------|------------|
|`_umul128`|x64|\<intrin.h>|

## <a name="example"></a>Przykład

```C
// umul128.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_umul128)

int main()
{
    unsigned __int64 a = 0x0fffffffffffffffI64;
    unsigned __int64 b = 0xf0000000I64;
    unsigned __int64 c, d;

    d = _umul128(a, b, &c);

    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
