---
description: 'Dowiedz się więcej na temat: _CIlog10'
title: _CIlog10
ms.date: 4/2/2020
api_name:
- _CIlog10
- _o__CIlog10
api_location:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIlog10
- _CIlog10
helpviewer_keywords:
- _CIlog10 intrinsic
- CIlog10 intrinsic
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
ms.openlocfilehash: e10dbe43eb9799b62a0ede515efaf75658fee932
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209649"
---
# <a name="_cilog10"></a>_CIlog10

Wykonuje `log10` operację na najwyższej wartości na stosie.

## <a name="syntax"></a>Składnia

```cpp
void __cdecl _CIlog10();
```

## <a name="remarks"></a>Uwagi

Ta wersja `log10` funkcji ma wyspecjalizowaną konwencję wywoływania, którą rozpoznaje kompilator. Funkcja przyspiesza wykonywanie, ponieważ uniemożliwia generowanie kopii i pomaga w zarejestrowaniu alokacji.

Wartość wyników jest wypychana na górze stosu.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](global-state.md).

## <a name="requirements"></a>Wymagania

**Platforma:** x86

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)
