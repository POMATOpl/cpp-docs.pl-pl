---
title: _CItan
ms.date: 04/11/2018
api_name:
- _CItan
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CItan
- CItan
helpviewer_keywords:
- CItan intrinsic
- _CItan intrinsic
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
ms.openlocfilehash: e509d785648148e51004950076147b69c2db18ec
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940467"
---
# <a name="_citan"></a>_CItan

Oblicza tangens górnej wartości na stosie zmiennoprzecinkowym.

## <a name="syntax"></a>Składnia

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Uwagi

Ta wersja funkcji [Tan](../c-runtime-library/reference/tan-tanf-tanl.md) ma wyspecjalizowaną konwencję wywoływania, którą rozpoznaje kompilator. Funkcja przyspiesza wykonywanie, ponieważ uniemożliwia generowanie kopii i pomaga w zarejestrowaniu alokacji.

Wartość wyników jest wypychana na górze stosu zmiennoprzecinkowego.

## <a name="requirements"></a>Wymagania

**Platforma:** x86

## <a name="see-also"></a>Zobacz także

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
