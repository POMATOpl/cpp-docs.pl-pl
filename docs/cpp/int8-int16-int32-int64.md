---
description: 'Dowiedz się więcej na temat: __int8, __int16, __int32 __int64'
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 8dddb8dc63b8aa9898b78ee02ea2dc904b362442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332510"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**specyficzne dla firmy Microsoft**

Funkcje Microsoft C/C++ obsługują typy liczb całkowitych. Można zadeklarować 8-, 16-, 32-lub 64-bitowe zmienne całkowite przy użyciu **`__intN`** specyfikatora typu, gdzie * *_`N`_* _ to 8, 16, 32 lub 64.

Poniższy przykład deklaruje jedną zmienną dla każdego z tych typów liczb całkowitych:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Typy _ * * `__int8` *, **`__int16`** i **`__int32`** są synonimami dla typów ANSI, które mają taki sam rozmiar i są przydatne do pisania kodu przenośnego, który działa identycznie na wielu platformach. **`__int8`** Typ danych jest synonimem typu **`char`** , **`__int16`** jest synonimem typu **`short`** i **`__int32`** jest synonimem typu **`int`** . **`__int64`** Typ jest synonimem typu **`long long`** .

W celu zapewnienia zgodności z poprzednimi wersjami,,, **`_int8`** **`_int16`** **`_int32`** i **`_int64`** są synonimami dla **`__int8`** , **`__int16`** , **`__int32`** i, **`__int64`** chyba że opcja kompilatora [ `/Za` \( Wyłącz rozszerzenia języka)](../build/reference/za-ze-disable-language-extensions.md) jest określona.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, że `__intN` parametr zostanie podwyższony do **`int`** :

```cpp
// sized_int_types.cpp

#include <stdio.h>

void func(int i) {
    printf_s("%s\n", __FUNCTION__);
}

int main()
{
    __int8 i8 = 100;
    func(i8);   // no void func(__int8 i8) function
                // __int8 will be promoted to int
}
```

```Output
func
```

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[Typy wbudowane](../cpp/fundamental-types-cpp.md)<br/>
[Zakresy typów danych](../cpp/data-type-ranges.md)<br/>
