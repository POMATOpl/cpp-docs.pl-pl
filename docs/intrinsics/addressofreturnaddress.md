---
description: 'Dowiedz się więcej na temat: _AddressOfReturnAddress'
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 1a79ccbe7ddc2865d8225a62cd0d294f0bc66b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331923"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Specyficzne dla firmy Microsoft**

Udostępnia adres lokalizacji pamięci, która przechowuje adres zwrotny bieżącej funkcji. Tego adresu nie można używać do uzyskiwania dostępu do innych lokalizacji pamięci (na przykład argumentów funkcji).

## <a name="syntax"></a>Składnia

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64, ARM, ARM64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Gdy `_AddressOfReturnAddress` jest używany w programie skompilowanym z [/CLR](../build/reference/clr-common-language-runtime-compilation.md), funkcja zawierająca `_AddressOfReturnAddress` wywołanie jest kompilowana jako funkcja natywna. Gdy funkcja skompilowana jako wywołania zarządzane do funkcji zawierającej `_AddressOfReturnAddress` , `_AddressOfReturnAddress` może nie zachowywać się zgodnie z oczekiwaniami.

Ta procedura jest dostępna tylko jako wewnętrzna.

## <a name="example"></a>Przykład

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
