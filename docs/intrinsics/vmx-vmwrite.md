---
description: 'Dowiedz się więcej na temat: __vmx_vmwrite'
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: d8902d51b05fa96faf22cbb6d80400e1f67c5f3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257306"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Specyficzne dla firmy Microsoft**

Zapisuje określoną wartość do określonego pola w bieżącej strukturze sterowania maszyną wirtualną (VMCS).

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>Parametry

*Polami*\
podczas Pole VMCS, które ma zostać zapisane.

*FieldValue*\
podczas Wartość do zapisu w polu VMCS.

## <a name="return-value"></a>Wartość zwracana

2,0
Operacja zakończyła się pomyślnie.

jedno
Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.

dwóch
Operacja nie powiodła się bez dostępnego stanu.

## <a name="remarks"></a>Uwagi

`__vmx_vmwrite`Funkcja jest równoważna z `VMWRITE` instrukcją maszyny. Wartość `Field` parametru jest zakodowanym indeksem pola, który jest opisany w dokumentacji firmy Intel. Aby uzyskać więcej informacji, Wyszukaj dodatek C "Specyfikacja techniczna wirtualizacji firmy Intel dla architektury Intel o architekturze IA-32" w witrynie [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
