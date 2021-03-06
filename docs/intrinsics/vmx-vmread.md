---
description: 'Dowiedz się więcej na temat: __vmx_vmread'
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 39ea9c0566d3f9c9d3fc6d980861fb3580293895
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333505"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Specyficzne dla firmy Microsoft**

Odczytuje określone pole z bieżącej struktury kontrolnej maszyny wirtualnej (VMCS) i umieszcza je w określonej lokalizacji.

## <a name="syntax"></a>Składnia

```C
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

### <a name="parameters"></a>Parametry

*Polami*\
podczas Pole VMCS, które ma zostać odczytane.

*FieldValue*\
podczas Wskaźnik do lokalizacji, do której ma być przechowywana wartość odczytana z pola VMCS określonego przez `Field` parametr.

## <a name="return-value"></a>Wartość zwracana

|Wartość|Znaczenie|
|-----------|-------------|
|0|Operacja zakończyła się pomyślnie.|
|1|Operacja nie powiodła się z rozszerzonym stanem dostępnym w `VM-instruction error field` bieżącym VMCs.|
|2|Operacja nie powiodła się bez dostępnego stanu.|

## <a name="remarks"></a>Uwagi

`__vmx_vmread`Funkcja jest równoważna z `VMREAD` instrukcją maszyny. Wartość `Field` parametru jest zakodowanym indeksem pola, który jest opisany w dokumentacji firmy Intel. Aby uzyskać więcej informacji, Wyszukaj dodatek C "Specyfikacja techniczna wirtualizacji firmy Intel dla architektury Intel o architekturze IA-32" w witrynie [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__vmx_vmread`|x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
