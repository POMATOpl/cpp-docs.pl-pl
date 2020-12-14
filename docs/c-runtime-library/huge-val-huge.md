---
description: 'Dowiedz się więcej na temat: HUGE_VAL, _HUGE'
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
api_name:
- _HUGE
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: c4109b61b9af65681ca2a006a3839e3d0338fa73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253146"
---
# <a name="huge_val-_huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Składnia

```
#include <math.h>
```

## <a name="remarks"></a>Uwagi

`HUGE_VAL` jest największą reprezentacją podwójnej wartości. Ta wartość jest zwracana przez wiele funkcji matematycznych w czasie wykonywania w przypadku wystąpienia błędu. Dla niektórych funkcji — `HUGE_VAL` jest zwracany. `HUGE_VAL` jest zdefiniowany jako `_HUGE` , ale funkcje matematyczne w czasie wykonywania zwracają `HUGE_VAL` . Należy również użyć `HUGE_VAL` w kodzie, aby zapewnić spójność.

## <a name="see-also"></a>Zobacz też

[Stałe globalne](../c-runtime-library/global-constants.md)
