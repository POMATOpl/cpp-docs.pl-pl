---
description: 'Dowiedz się więcej na temat: __umulh'
title: __umulh
ms.date: 09/02/2019
f1_keywords:
- __umulh
helpviewer_keywords:
- __umulh intrinsic
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
ms.openlocfilehash: 1d727d72155bdfb5cd5da1ee56c514af26b5ae89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333618"
---
# <a name="__umulh"></a>__umulh

**Specyficzne dla firmy Microsoft**

Zwróć wysoki 64 bitów iloczynu 2 64-bitowych liczb całkowitych bez znaku.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __umulh(
   unsigned __int64 a,
   unsigned __int64 b
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
|`__umulh`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Te procedury są dostępne tylko jako elementy wewnętrzne.

## <a name="example"></a>Przykład

```cpp
// umulh.cpp
// processor: X64
#include <cstdio>
#include <intrin.h>

int main()
{
    unsigned __int64 i = 0x10;
    unsigned __int64 j = 0xFEDCBA9876543210;
    unsigned __int64 k = i * j; // k has the low 64 bits
                                // of the product.
    unsigned __int64 result;
    result = __umulh(i, j); // result has the high 64 bits
                            // of the product.
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);
    return 0;
}
```

```Output
0x10 * 0xfedcba9876543210 = 0xfedcba98765432100
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
