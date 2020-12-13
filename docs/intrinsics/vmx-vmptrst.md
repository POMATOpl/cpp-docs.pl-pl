---
description: 'Dowiedz się więcej na temat: __vmx_vmptrst'
title: __vmx_vmptrst
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 216da453acf5c04e4189271185567841327571ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333526"
---
# <a name="__vmx_vmptrst"></a>__vmx_vmptrst

**Specyficzne dla firmy Microsoft**

Przechowuje wskaźnik do bieżącej struktury sterowania maszyną wirtualną (VMCS) pod określonym adresem.

## <a name="syntax"></a>Składnia

```C
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmcsPhysicalAddress*\
podczas Adres, w którym jest przechowywany bieżący wskaźnik VMCS.

## <a name="remarks"></a>Uwagi

Wskaźnik VMCS jest 64-bitowym adresem fizycznym.

`__vmx_vmptrst`Funkcja jest równoważna z `VMPTRST` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32", a następnie w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002".

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)
