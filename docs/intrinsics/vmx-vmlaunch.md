---
description: 'Dowiedz się więcej na temat: __vmx_vmlaunch'
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 3f6596e0644250710491ed90036a651c0725a5f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333554"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Specyficzne dla firmy Microsoft**

Umieszcza aplikację wywołującą w niegłównym stanie operacji VMX (Enter VM) przy użyciu bieżącej struktury kontroli maszyny wirtualnej (VMCS).

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>Wartość zwracana

|Wartość|Znaczenie|
|-----------|-------------|
|0|Operacja zakończyła się pomyślnie.|
|1|Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.|
|2|Operacja nie powiodła się bez dostępnego stanu.|

## <a name="remarks"></a>Uwagi

Aplikacja może wykonać operację wprowadzania do maszyny wirtualnej za pomocą funkcji [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) lub [__vmx_vmresume](../intrinsics/vmx-vmresume.md) . Funkcja [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) może być używana tylko z VMCs o stanie uruchamiania `Clear` , a funkcja [__vmx_vmresume](../intrinsics/vmx-vmresume.md) może być używana tylko z VMCs, którego stanem uruchamiania jest `Launched` . W związku z tym Użyj funkcji [__vmx_vmclear](../intrinsics/vmx-vmclear.md) , aby ustawić stan uruchamiania VMCs na `Clear` , a następnie użyć funkcji [__VMX_VMLAUNCH](../intrinsics/vmx-vmlaunch.md) dla pierwszej operacji vm-Enter i funkcji [__vmx_vmresume](../intrinsics/vmx-vmresume.md) dla kolejnych operacji wejścia-wyjścia.

`__vmx_vmlaunch`Funkcja jest równoważna z `VMLAUNCH` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32", a następnie w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002".

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmlaunch`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
