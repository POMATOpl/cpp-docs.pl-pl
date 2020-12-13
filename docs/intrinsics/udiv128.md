---
description: 'Dowiedz się więcej na temat: _udiv128'
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: f88546a179106f4291fcaeb865f1aad9e67c4045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333652"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128`Wewnętrznie dzieli 128-bitową liczbę całkowitą bez znaku przez 64-bitową liczbę całkowitą bez znaku. Wartość zwracana utrzymuje iloraz, a wewnętrzna Zwraca resztę za pomocą parametru wskaźnika. `_udiv128` jest **specyficzny dla firmy Microsoft**.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Parametry

*highDividend* \
podczas Wysoka 64 bitów dywidendy.

*lowDividend* \
podczas Niska 64 bitów dywidendy.

*dzielnik* \
podczas 64-bitowa liczba całkowita do podzielenia przez.

*pozostałej części* \
określoną 64-bitowe całkowite bity reszty.

## <a name="return-value"></a>Wartość zwracana

64 bitów ilorazu.

## <a name="remarks"></a>Uwagi

Przekaż górne 64 bitów z 128-bitowej dywidendy w *highDividend* i niższą 64 bity w *lowDividend*. Wewnętrznie dzieli tę wartość przez *dzielnik*. Przechowuje resztę z 64-bitowej liczby całkowitej bez znaku wskazywanej przez *resztę* i zwraca 64 bitów ilorazu.

Funkcja `_udiv128` wewnętrzna jest dostępna od wersji Visual Studio 2019 RTM.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|Nagłówek|
|---------------|------------------|------------|
|`_udiv128`|x64|\<immintrin.h>|

## <a name="see-also"></a>Zobacz też

[_div128](div128.md) \
[Funkcje wewnętrzne kompilatora](compiler-intrinsics.md)
