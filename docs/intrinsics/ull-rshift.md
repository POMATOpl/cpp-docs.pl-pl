---
description: 'Dowiedz się więcej na temat: __ull_rshift'
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: 5b819e4a1df8db7b7562023c6acc9dbbd94f7f76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333630"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Specyficzne dla firmy Microsoft**

w wersji x64 program przenosi wartość 64-bitową określoną przez pierwszy parametr w prawo przez liczbę bitów określoną przez drugi parametr.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask,
   int nBit
);
```

### <a name="parameters"></a>Parametry

*bitowa*\
podczas Wartość 64-bitowa liczba całkowita, która ma zostać przesunięta w prawo.

*nBit*\
podczas Liczba bitów do przesunięcia, modulo 32 w x86 i modulo 64 w x64.

## <a name="return-value"></a>Wartość zwracana

Maska przesunięta przez `nBit` bity.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Jeśli drugi parametr jest większy niż 31 na x86 (63 na x64), ta liczba jest pobierana modulo 32 (64 on x64), aby określić liczbę bitów do przesunięcia. Wartość `ull` w polu Nazwa wskazuje `unsigned long long (unsigned __int64)` .

## <a name="example"></a>Przykład

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
