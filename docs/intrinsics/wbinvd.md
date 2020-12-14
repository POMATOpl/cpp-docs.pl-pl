---
description: 'Dowiedz się więcej na temat: __wbinvd'
title: __wbinvd
ms.date: 09/02/2019
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: b40e1b618e49ab317a7b9cdeea647bcd58df7912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257267"
---
# <a name="__wbinvd"></a>__wbinvd

**Specyficzne dla firmy Microsoft**

Generuje instrukcję Write-back i unvalidate cache ( `wbinvd` ).

## <a name="syntax"></a>Składnia

```C
void __wbinvd(void);
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__wbinvd`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta funkcja jest dostępna tylko w trybie jądra z poziomem uprawnień (CPL) o wartości 0, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
