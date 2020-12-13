---
description: 'Dowiedz się więcej na temat: __vmx_vmptrld'
title: __vmx_vmptrld
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: 850311e4423940ebd34a203e6d43ec961b3258f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333538"
---
# <a name="__vmx_vmptrld"></a>__vmx_vmptrld

**Specyficzne dla firmy Microsoft**

Ładuje wskaźnik do bieżącej struktury kontroli maszyny wirtualnej (VMCS) z podanego adresu.

## <a name="syntax"></a>Składnia

```C
int __vmx_vmptrld(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmcsPhysicalAddress*\
podczas Adres, w którym jest przechowywany wskaźnik VMCS.

## <a name="return-value"></a>Wartość zwracana

2,0
Operacja zakończyła się pomyślnie.

jedno
Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.

dwóch
Operacja nie powiodła się bez dostępnego stanu.

## <a name="remarks"></a>Uwagi

Wskaźnik VMCS jest 64-bitowym adresem fizycznym.

`__vmx_vmptrld`Funkcja jest równoważna z `VMPTRLD` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32", a następnie w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002".

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmptrld`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)
