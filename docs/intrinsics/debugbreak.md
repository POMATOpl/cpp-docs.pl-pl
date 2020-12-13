---
description: 'Dowiedz się więcej na temat: __debugbreak'
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 83a670d9fa9c1f6b41c1c405c59af71c7aa0c8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337112"
---
# <a name="__debugbreak"></a>__debugbreak

**Specyficzne dla firmy Microsoft**

Powoduje, że punkt przerwania w kodzie, w którym użytkownik zostanie poproszony o uruchomienie debugera.

## <a name="syntax"></a>Składnia

```C
void __debugbreak();
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|Nagłówek|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Uwagi

`__debugbreak`Wewnętrzny kompilator, podobny do [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak), jest przenośnym sposobem na działanie punktu przerwania.

> [!NOTE]
> Podczas kompilowania z **/CLR**, funkcja zawierająca `__debugbreak` zostanie skompilowana do MSIL. `asm int 3` powoduje, że funkcja jest skompilowana do kodu natywnego. Aby uzyskać więcej informacji, zobacz [__asm](../assembler/inline/asm.md).

Na przykład:

```C
main() {
   __debugbreak();
}
```

jest podobny do:

```C
main() {
   __asm {
      int 3
   }
}
```

na komputerze z procesorem x86.

W programie ARM64 `__debugbreak` wewnętrznie jest kompilowane do instrukcji `brk #0xF000` .

Ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
