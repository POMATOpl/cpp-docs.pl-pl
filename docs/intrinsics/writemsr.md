---
description: 'Dowiedz się więcej na temat: __writemsr'
title: __writemsr
ms.date: 09/02/2019
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: 0ab7392d9df07a9083ca095bc7002a6bf7d45628
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331850"
---
# <a name="__writemsr"></a>__writemsr

**Specyficzne dla firmy Microsoft**

Generuje instrukcję Write do specyficznego dla modelu rejestru ( `wrmsr` ).

## <a name="syntax"></a>Składnia

```C
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

### <a name="parameters"></a>Parametry

*Zarejestrować*\
podczas Rejestr specyficzny dla modelu.

*Wartościami*\
podczas Wartość do zapisania.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__writemsr`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta funkcja może być używana tylko w trybie jądra, a ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
