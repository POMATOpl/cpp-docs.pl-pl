---
title: _CIlog
ms.date: 4/2/2020
api_name:
- _CIlog
- _o__CIlog
api_location:
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIlog
- CIlog
helpviewer_keywords:
- _CIlog intrinsic
- CIlog intrinsic
ms.assetid: 23503854-ddaa-4fe0-a4a3-7fbb3a43bdec
ms.openlocfilehash: 0203c40395c99fc145e1c8125f5d40c0d43571fc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745392"
---
# <a name="_cilog"></a>_CIlog

Oblicza logarytm naturalny najwyższej wartości w stosie.

## <a name="syntax"></a>Składnia

```cpp
void __cdecl _CIlog();
```

## <a name="remarks"></a>Uwagi

Ta wersja `log` funkcji ma wyspecjalizowaną konwencję wywoływania, którą kompilator rozumie. Przyspiesza wykonanie, ponieważ zapobiega generowaniu kopii i pomaga w alokacji rejestru.

Wynikowa wartość jest wypychany na górze stosu.

Domyślnie stan globalny tej funkcji jest ograniczony do aplikacji. Aby to zmienić, zobacz [Stan globalny w crt](global-state.md).

## <a name="requirements"></a>Wymagania

**Platforma:** x86

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)
