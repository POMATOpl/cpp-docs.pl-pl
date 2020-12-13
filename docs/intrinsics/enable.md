---
description: 'Dowiedz się więcej na temat: _enable'
title: _enable
ms.date: 09/02/2019
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: b9c84a31869dd356d5ee6ebd4eae5bd579cf319e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337039"
---
# <a name="_enable"></a>_enable

**Specyficzne dla firmy Microsoft**

Włącza przerwy.

## <a name="syntax"></a>Składnia

```C
void _enable(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_enable`|x86, ARM, x64, ARM64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_enable` powoduje, że procesor ustawi flagę przerwania. W systemach x86 ta funkcja generuje instrukcję SET Interrupt flag ( `sti` ).

Ta funkcja jest dostępna tylko w trybie jądra. W przypadku użycia w trybie użytkownika zostanie zgłoszony wyjątek uprzywilejowanej instrukcji.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
