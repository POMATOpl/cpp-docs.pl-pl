---
description: 'Dowiedz się więcej na temat: __mulh'
title: __mulh
ms.date: 09/02/2019
f1_keywords:
- __mulh
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
ms.openlocfilehash: 0cee31b6a9e1088d76200cd46482fd4aaf80474b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118943"
---
# <a name="__mulh"></a>__mulh

**Specyficzne dla firmy Microsoft**

Zwraca wysoki 64 bitów iloczynu 2 64-bitowych liczb całkowitych ze znakiem.

## <a name="syntax"></a>Składnia

```C
__int64 __mulh(
   __int64 a,
   __int64 b
);
```

### <a name="parameters"></a>Parametry

*z*\
podczas Pierwsza liczba do pomnożenia.

*b*\
podczas Druga liczba do pomnożenia.

## <a name="return-value"></a>Wartość zwracana

Wysokie 64 bitów wynik 128-bitowego mnożenia.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__mulh`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta procedura jest dostępna tylko jako wewnętrzna.

## <a name="example"></a>Przykład

```cpp
// mulh.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__mulh)

int main()
{
    __int64 a = 0x0fffffffffffffffI64;
    __int64 b = 0xf0000000I64;

    __int64 result = __mulh(a, b); // the high 64 bits
    __int64 result2 = a * b; // the low 64 bits

    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",
             a, b, result, result2);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
