---
description: 'Dowiedz się więcej na temat: _mm_cvttss_si64x'
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: a4af7b726d0f15099586bc94348ab4ba7ebf5b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167633"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Specyficzne dla firmy Microsoft**

Emituje rozszerzoną wersję architektury Convert z obcinaniem Single-Precision Floating-Point liczbą do 64-bitową liczbę całkowitą ( `cvttss2si` ).

## <a name="syntax"></a>Składnia

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Parametry

*wartościami*\
podczas **`__m128`** Struktura zawierająca wartości zmiennoprzecinkowe o pojedynczej precyzji.

## <a name="return-value"></a>Wartość zwracana

Wynik konwersji pierwszej wartości zmiennoprzecinkowej na 64-bitową liczbę całkowitą.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_mm_cvttss_si64x`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Wewnętrznie różni się od `_mm_cvtss_si64x` tylko w tym, że konwersje niedokładne są obcinane w kierunku zera. Ponieważ **`__m128`** Struktura reprezentuje rejestr XMM, wygenerowana instrukcja przenosi dane z rejestru XMM do pamięci systemowej.

Ta procedura jest dostępna tylko jako wewnętrzna.

## <a name="example"></a>Przykład

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__m128](../cpp/m128.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
