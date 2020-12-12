---
description: 'Dowiedz się więcej na temat: __nop'
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 55759e8324511b6ddaa2774bdfdc3554c0032c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118930"
---
# <a name="__nop"></a>__nop

**Specyficzne dla firmy Microsoft**

Generuje kod maszynowy specyficzny dla platformy, który nie wykonuje operacji.

## <a name="syntax"></a>Składnia

```C
void __nop();
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="remarks"></a>Uwagi

`__nop`Funkcja jest równoważna z `NOP` instrukcją maszyny. Aby uzyskać więcej informacji na temat architektury x86 i x64, Wyszukaj dokument "Podręcznik Intel Architecture Developer, Tom 2: odwołanie do zestawu instrukcji" w witrynie [firmy Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
