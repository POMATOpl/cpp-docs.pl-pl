---
description: 'Dowiedz się więcej na temat: _acmdln, _tcmdln, _wcmdln'
title: _acmdln, _tcmdln, _wcmdln
ms.date: 11/04/2016
api_name:
- _wcmdln
- _acmdln
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
ms.openlocfilehash: cc47e6e48e408ebd0a4edc02048d6c40ae638ecd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242694"
---
# <a name="_acmdln-_tcmdln-_wcmdln"></a>_acmdln, _tcmdln, _wcmdln

Wewnętrzna zmienna globalna CRT. Wiersz polecenia.

## <a name="syntax"></a>Składnia

```
char * _acmdln;
wchar_t * _wcmdln;

#ifdef WPRFLAG
   #define _tcmdln _wcmdln
#else
   #define _tcmdln _acmdln
```

## <a name="remarks"></a>Uwagi

Te zmienne wewnętrzne CRT przechowują kompletny wiersz polecenia. Są one widoczne w eksportowanych symbolach CRT, ale nie są przeznaczone do użycia w kodzie. `_acmdln` przechowuje dane jako ciąg znaków. `_wcmdln` dane są przechowywane jako ciąg znaków dwubajtowych. `_tcmdln` można zdefiniować jako `_acmdln` lub `_wcmdln` , w zależności od tego, który jest odpowiedni.

## <a name="see-also"></a>Zobacz też

[Zmienne globalne](../c-runtime-library/global-variables.md)
