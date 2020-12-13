---
description: 'Dowiedz się więcej na temat: __svm_vmload'
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: 975f6aed50007b0b184bbab2b9b48790e5e20616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333711"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Specyficzne dla firmy Microsoft**

Ładuje podzestaw stanu procesora z określonego bloku sterowania maszyną wirtualną (VMCB).

## <a name="syntax"></a>Składnia

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmcbPhysicalAddress*\
podczas Adres fizyczny VMCB.

## <a name="remarks"></a>Uwagi

`__svm_vmload`Funkcja jest równoważna z `VMLOAD` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument ", wersja zavisioned Architecture", Tom 2: Programowanie systemu, "numer dokumentu 24593, Poprawka 3,11, w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
