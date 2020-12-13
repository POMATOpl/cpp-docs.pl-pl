---
description: 'Dowiedz się więcej na temat: __vmx_on'
title: __vmx_on
ms.date: 09/02/2019
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: a1e9171fe64a239b592f0d27ec49d4159b46523d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333571"
---
# <a name="__vmx_on"></a>__vmx_on

**Specyficzne dla firmy Microsoft**

Aktywuje operacje rozszerzenia maszyny wirtualnej (VMX) w procesorze.

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmsSupportPhysicalAddress*\
podczas Wskaźnik do 64-bitowego adresu fizycznego, który wskazuje na strukturę sterowania maszyną wirtualną (VMCS).

## <a name="return-value"></a>Wartość zwracana

|Wartość|Znaczenie|
|-----------|-------------|
|0|Operacja zakończyła się pomyślnie.|
|1|Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.|
|2|Operacja nie powiodła się bez dostępnego stanu.|

## <a name="remarks"></a>Uwagi

`__vmx_on`Funkcja odnosi się do `VMXON` instrukcji Machine. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32", a następnie w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002".

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_on`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
