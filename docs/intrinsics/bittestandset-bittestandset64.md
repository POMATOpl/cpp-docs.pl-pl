---
description: 'Dowiedz się więcej na temat: _bittestandset, _bittestandset64'
title: _bittestandset, _bittestandset64
ms.date: 09/02/2019
f1_keywords:
- _bittestandset_cpp
- _bittestandset64_cpp
- _bittestandset64
- _bittestandset
helpviewer_keywords:
- bts instruction
- _bittestandset intrinsic
- _bittestandset64 intrinsic
ms.assetid: 6d6c8670-fea0-4c1c-9aad-2bb842715203
ms.openlocfilehash: 69d1c8569a228ed4994343e12ef769710bd06ad5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337151"
---
# <a name="_bittestandset-_bittestandset64"></a>_bittestandset, _bittestandset64

**Specyficzne dla firmy Microsoft**

Wygeneruj instrukcję, aby przeanalizować bit `b` adresu `a` , zwrócić jego bieżącą wartość i ustawić bit na 1.

## <a name="syntax"></a>Składnia

```C
unsigned char _bittestandset(
   long *a,
   long b
);
unsigned char _bittestandset64(
   __int64 *a,
   __int64 b
);
```

### <a name="parameters"></a>Parametry

*z*\
[in. out] Wskaźnik do pamięci do sprawdzenia.

*b*\
podczas Pozycja bitu do przetestowania.

## <a name="return-value"></a>Wartość zwracana

Bit w określonym położeniu.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_bittestandset`|x86, ARM, x64, ARM64|
|`_bittestandset64`|x64, ARM64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta procedura jest dostępna tylko jako wewnętrzna.

## <a name="example"></a>Przykład

```cpp
// bittestandset.cpp
// processor: x86, ARM, x64
// This example uses several of the _bittest family of intrinsics
// to implement a Flags class that allows bit level access to an
// integer field.
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_bittestandset, _bittestandreset,\
                  _bittestandcomplement, _bittest)

class Flags
{
private:
    long flags;
    long* oldValues;

public:
    Flags() : flags(0)
    {
        oldValues = new long[32];
    }

    ~Flags()
    {
        delete oldValues;
    }

    void SetFlagBit(long nBit)
    {
        // We omit range checks on the argument
        oldValues[nBit] = _bittestandset(&flags, nBit);
        printf_s("Flags: 0x%x\n", flags);
    }
    void ClearFlagBit(long nBit)
    {
        oldValues[nBit] = _bittestandreset(&flags, nBit);
        printf_s("Flags: 0x%x\n", flags);
    }
    unsigned char GetFlagBit(long nBit)
    {
        unsigned char result = _bittest(&flags, nBit);
        printf_s("Flags: 0x%x\n", flags);
        return result;
    }
    void RestoreFlagBit(long nBit)
    {
        if (oldValues[nBit])
            oldValues[nBit] = _bittestandset(&flags, nBit);
        else
            oldValues[nBit] = _bittestandreset(&flags, nBit);
        printf_s("Flags: 0x%x\n", flags);
    }
    unsigned char ToggleBit(long nBit)
    {
        unsigned char result = _bittestandcomplement(&flags, nBit);
        printf_s("Flags: 0x%x\n", flags);
        return result;
    }
};

int main()
{
    Flags f;
    f.SetFlagBit(1);
    f.SetFlagBit(2);
    f.SetFlagBit(3);
    f.ClearFlagBit(3);
    f.ToggleBit(1);
    f.RestoreFlagBit(2);
}
```

```Output
Flags: 0x2
Flags: 0x6
Flags: 0xe
Flags: 0x6
Flags: 0x4
Flags: 0x0
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
