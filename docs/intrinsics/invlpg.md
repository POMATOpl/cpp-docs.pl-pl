---
description: 'Dowiedz się więcej na temat: __invlpg'
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 16d8f51c8bf36ea94be7b1325ee5bed256c29693
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167906"
---
# <a name="__invlpg"></a>__invlpg

**Specyficzne dla firmy Microsoft**

Generuje instrukcję x86 `invlpg` , która unieważnia bufor tłumaczenia referencyjna (TLB) dla strony skojarzonej z pamięcią wskazywaną przez *adres*.

## <a name="syntax"></a>Składnia

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>Parametry

*Ulica*\
podczas Adres 64-bitowy.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Wewnętrznie `__invlpg` emituje uprzywilejowaną instrukcję i jest dostępna tylko w trybie jądra z poziomem uprawnień (CPL) równym 0.

Ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
