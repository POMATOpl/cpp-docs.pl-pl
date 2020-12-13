---
description: 'Dowiedz się więcej na temat: __vmx_vmresume'
title: __vmx_vmresume
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmresume
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
ms.openlocfilehash: 35c1ca7eeca847b14d16c451752a186c63a59749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343781"
---
# <a name="__vmx_vmresume"></a>__vmx_vmresume

**Specyficzne dla firmy Microsoft**

Wznawia operację niegłówną VMX przy użyciu bieżącej struktury kontrolnej maszyny wirtualnej (VMCS).

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_vmresume(
   void);
```

## <a name="return-value"></a>Wartość zwracana

|Wartość|Znaczenie|
|-----------|-------------|
|0|Operacja zakończyła się pomyślnie.|
|1|Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.|
|2|Operacja nie powiodła się bez dostępnego stanu.|

## <a name="remarks"></a>Uwagi

Aplikacja może wykonać operację wprowadzania do maszyny wirtualnej za pomocą polecenia [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) lub `__vmx_vmresume` funkcji. `__vmx_vmlaunch`Funkcja może być używana tylko z VMCs o stanie uruchamiania `Clear` , a `__vmx_vmresume` Funkcja może być używana tylko z VMCs, którego stanem uruchamiania jest `Launched` . W związku z tym Użyj funkcji [__vmx_vmclear](../intrinsics/vmx-vmclear.md) , aby ustawić stan uruchamiania VMCs na `Clear` , a następnie użyć `__vmx_vmlaunch` funkcji dla pierwszej maszyny wirtualnej — wprowadź operację i `__vmx_vmresume` funkcję dla kolejnych maszyn wirtualnych — wprowadź operacje.

`__vmx_vmresume`Funkcja jest równoważna z `VMRESUME` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument PDF "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32" w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmresume`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
