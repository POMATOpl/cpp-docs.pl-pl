---
description: 'Dowiedz się więcej na temat: __lzcnt16, __lzcnt, __lzcnt64'
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 09/02/2019
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: 75e2c105d05cfe4620f558a4f44c8ae8b9cd6f8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167737"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Specyficzne dla firmy Microsoft**

Oblicza liczbę zer wiodących w 16-, 32-lub 64-bitowej liczbie całkowitej.

## <a name="syntax"></a>Składnia

```C
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Parametry

*wartościami*\
podczas 16-, 32-lub 64-bitowa liczba całkowita bez znaku do skanowania dla zer wiodących.

## <a name="return-value"></a>Wartość zwracana

Liczba wiodących bitów zerowych w `value` parametrze. Jeśli `value` jest równa zero, wartość zwracana jest rozmiar operandu wejściowego (16, 32 lub 64). Jeśli najbardziej znaczący bit `value` jest taki, wartość zwracana wynosi zero.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__lzcnt16`|AMD: Zaawansowane manipulowanie Bitmi (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: Zaawansowane manipulowanie Bitmi (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD: Zaawansowane manipulowanie bitowymi (ABM) w trybie 64-bitowym.<br /><br /> Intel: Haswell|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Każda z elementów wewnętrznych generuje `lzcnt` instrukcję.  Rozmiar wartości `lzcnt` zwracanej przez instrukcję jest taki sam, jak rozmiar tego argumentu.  W trybie 32-bitowym nie ma żadnych 64-bitowych rejestrów ogólnego przeznaczenia, dlatego 64-bit `lzcnt` nie jest obsługiwane.

Aby określić obsługę sprzętową `lzcnt` instrukcji, wywołaj `__cpuid` wewnętrzne z `InfoType=0x80000001` i sprawdź bit 5 z `CPUInfo[2] (ECX)` . Ten bit będzie miał wartość 1, jeśli instrukcja jest obsługiwana i 0 w przeciwnym razie. Jeśli uruchamiasz kod, który używa wewnętrznego na sprzęcie, który nie obsługuje `lzcnt` instrukcji, wyniki są nieprzewidywalne.

W przypadku procesorów Intel, które nie obsługują `lzcnt` instrukcji, kodowanie bajtów instrukcji jest wykonywane jako `bsr` (skanowanie w odwrotnej wersji). Jeśli przenośność kodu jest istotna, rozważ użycie `_BitScanReverse` wewnętrznie zamiast. Aby uzyskać więcej informacji, zobacz [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Przykład

```cpp
// Compile this test with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

Częścią tej zawartości są Copyright 2007 (Advanced Micro Devices, Inc.). Wszelkie prawa zastrzeżone. Wygenerowane z uprawnieniami z zaawansowanych urządzeń Micro Devices, Inc.

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
