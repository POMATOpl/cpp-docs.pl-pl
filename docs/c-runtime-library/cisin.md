---
title: _CIsin
ms.date: 04/10/2018
api_name:
- _CIsin
api_location:
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIsin
- _CIsin
helpviewer_keywords:
- _CIsin intrinsic
- CIsin intrinsic
ms.assetid: f215f39a-2341-4f1c-ba8e-cb522451ceb2
ms.openlocfilehash: 66f26e9fa4dd08d18b15deca4efa40c236e092c9
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944548"
---
# <a name="_cisin"></a>_CIsin

Oblicza sinus górnej wartości w stosie zmiennoprzecinkowym.

## <a name="syntax"></a>Składnia

```C
void __cdecl _CIsin();
```

## <a name="remarks"></a>Uwagi

Ta wewnętrzna wersja funkcji [Sin](../c-runtime-library/reference/sin-sinf-sinl.md) ma wyspecjalizowaną konwencję wywoływania, którą rozpoznaje kompilator. Przyspiesza to wykonywanie, ponieważ uniemożliwia generowanie kopii i pomaga w zarejestrowaniu alokacji.

Wartość wyników jest wypychana na górze stosu zmiennoprzecinkowego.

## <a name="requirements"></a>Wymagania

**Platforma:** x86

## <a name="see-also"></a>Zobacz także

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)<br/>
