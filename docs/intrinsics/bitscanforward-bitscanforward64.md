---
description: 'Dowiedz się więcej na temat: _BitScanForward, _BitScanForward64'
title: _BitScanForward, _BitScanForward64
ms.date: 09/02/2019
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 182f22b5350fcad7c3da9a0d6f6df36c0871a3e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337223"
---
# <a name="_bitscanforward-_bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Specyficzne dla firmy Microsoft**

Przeszukaj dane maski z co najmniej znaczących bitów (LSB) na najbardziej znaczący bit (MSB) dla zestawu bitów (1).

## <a name="syntax"></a>Składnia

```C
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

### <a name="parameters"></a>Parametry

*Indeks*\
określoną Załadowano z pozycją bitową pierwszego zestawu bit (1).

*Bitowa*\
podczas Wartość 32-bitowa lub 64-bitowa do wyszukania.

## <a name="return-value"></a>Wartość zwracana

0, jeśli maska jest równa zero; w przeciwnym razie.

## <a name="remarks"></a>Uwagi

Jeśli zostanie znaleziony bit zestawu, w pierwszym parametrze zostanie zwrócona pozycja bitu wynosząca bit pierwszego zestawu. Jeśli nie zostanie znaleziony żaden bit zestawu, zwracana jest wartość 0. w przeciwnym razie zostanie zwrócona 1.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64, ARM64|
|`_BitScanForward64`|ARM64, x64|

**Plik nagłówka**\<intrin.h>

## <a name="example"></a>Przykład

```cpp
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

```Input
12
```

```Output
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
