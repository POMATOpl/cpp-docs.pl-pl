---
description: 'Dowiedz się więcej na temat: _disable'
title: _disable
ms.date: 09/02/2019
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: c118315a4fea2dad401cc5c6f3621a8ec3b1794c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337098"
---
# <a name="_disable"></a>_disable

**Specyficzne dla firmy Microsoft**

Wyłącza przerwania.

## <a name="syntax"></a>Składnia

```C
void _disable(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`_disable`|x86, ARM, x64, ARM64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`_disable` instruuje procesor, aby wyczyścił flagę przerwania. W systemach x86 ta funkcja generuje instrukcję Clear Interrupt flag ( `cli` ).

Ta funkcja jest dostępna tylko w trybie jądra. W przypadku użycia w trybie użytkownika wyjątek uprzywilejowanych instrukcji jest zgłaszany w czasie wykonywania.

Na platformach ARM i ARM64 ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
