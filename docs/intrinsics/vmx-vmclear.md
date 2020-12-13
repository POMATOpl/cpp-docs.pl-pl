---
description: 'Dowiedz się więcej na temat: __vmx_vmclear'
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 2eec5c1189c6a798246a6dabfc731fb0166bc14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333562"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Specyficzne dla firmy Microsoft**

Inicjuje określoną strukturę sterowania maszyną wirtualną (VMCS) i ustawia jej stan uruchamiania na `Clear` .

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmcsPhysicalAddress*\
podczas Wskaźnik do 64-bitowej lokalizacji pamięci, która zawiera adres fizyczny VMCS do wyczyszczenia.

## <a name="return-value"></a>Wartość zwracana

|Wartość|Znaczenie|
|-----------|-------------|
|0|Operacja zakończyła się pomyślnie.|
|1|Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.|
|2|Operacja nie powiodła się bez dostępnego stanu.|

## <a name="remarks"></a>Uwagi

Aplikacja może wykonać operację wprowadzania do maszyny wirtualnej za pomocą funkcji [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) lub [__vmx_vmresume](../intrinsics/vmx-vmresume.md) . Funkcja [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) może być używana tylko z VMCs o stanie uruchamiania `Clear` , a funkcja [__vmx_vmresume](../intrinsics/vmx-vmresume.md) może być używana tylko z VMCs, którego stanem uruchamiania jest `Launched` . W związku z tym Użyj funkcji [__vmx_vmclear](../intrinsics/vmx-vmclear.md) , aby ustawić stan uruchamiania VMCs na `Clear` . Użyj funkcji [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) dla pierwszej operacji VM-Enter i funkcji [__vmx_vmresume](../intrinsics/vmx-vmresume.md) dla kolejnych maszyn wirtualnych — wprowadź operacje.

`__vmx_vmclear`Funkcja jest równoważna z `VMCLEAR` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument "Specyfikacja techniczna wirtualizacji Intel dla architektury Intel o architekturze IA-32", a następnie w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) "numer dokumentu C97063-002".

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmclear`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
