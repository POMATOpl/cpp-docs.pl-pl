---
description: 'Dowiedz się więcej na temat: __svm_invlpga'
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: dc976f535381fcfdfec0da5c1a280c4df281c114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314753"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Specyficzne dla firmy Microsoft**

Unieważnia wpis mapowania adresów w buforze przeszukiwania tłumaczenia komputera. Parametry określają adres wirtualny i identyfikator przestrzeni adresowej strony do unieważnienia.

## <a name="syntax"></a>Składnia

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>Parametry

*Vaddr*\
podczas Adres wirtualny strony do unieważnienia.

*as_id*\
podczas Identyfikator przestrzeni adresowej (ASID) strony do unieważnienia.

## <a name="remarks"></a>Uwagi

`__svm_invlpga`Funkcja jest równoważna z `INVLPGA` instrukcją maszyny. Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, Wyszukaj dokument ", wersja zavisioned Architecture", Tom 2: Programowanie systemu, "numer dokumentu 24593, Poprawka 3,11, w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
