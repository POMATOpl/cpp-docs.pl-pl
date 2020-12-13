---
description: 'Dowiedz się więcej na temat: __svm_vmrun'
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: c01716e496513aa11132fdfc95235a39c7277279
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333705"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Specyficzne dla firmy Microsoft**

Uruchamia wykonywanie kodu gościa maszyny wirtualnej odpowiadającego określonemu blokowi sterowania maszynom wirtualnym (VMCB).

## <a name="syntax"></a>Składnia

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parametry

*VmcbPhysicalAddress*\
podczas Adres fizyczny VMCB.

## <a name="remarks"></a>Uwagi

`__svm_vmrun`Funkcja używa minimalnej ilości informacji w VMCB, aby rozpocząć wykonywanie kodu gościa maszyny wirtualnej. Użyj funkcji [__svm_vmsave](../intrinsics/svm-vmsave.md) lub [__svm_vmload](../intrinsics/svm-vmload.md) , jeśli potrzebujesz więcej informacji do obsługi złożonego przerwania lub przełączenia się do innego gościa.

`__svm_vmrun`Funkcja jest równoważna z `VMRUN` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, wyszukaj ten dokument, "głośność dla programisty o architekturze AMD64 2: Programowanie systemu", "numer dokumentu 24593, wersja 3,11 lub nowsza" w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
