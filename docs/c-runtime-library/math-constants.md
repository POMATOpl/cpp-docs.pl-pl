---
title: Stałe matematyczne | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.constants
dev_langs:
- C++
helpviewer_keywords:
- M_PI constant
- M_PI_2 constant
- math constants
- M_2_PI constant
- M_1_PI constant
- M_E constant
- USE_MATH_DEFINES constant
- M_LOG2E constant
- M_LOG10E constant
- M_LN10 constant
- M_SQRT1_2 constant
- _USE_MATH_DEFINES constant
- M_PI_4 constant
- constants, math
- M_2_SQRTPI constant
- M_SQRT2 constant
- M_LN2 constant
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12a53aff22d55b8f99b05bf870276da1370fad13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081432"
---
# <a name="math-constants"></a>Stałe matematyczne

## <a name="syntax"></a>Składnia

```
#define _USE_MATH_DEFINES // for C++
#include <cmath>

#define _USE_MATH_DEFINES // for C
#include <math.h>
```

## <a name="remarks"></a>Uwagi

Następujące znaki są zdefiniowane dla wartości ich wskazanej wyrażeń:

|Symbol|Wyrażenie|Wartość|
|------------|----------------|-----------|
|M_E|e|2.71828182845904523536|
|M_LOG2E|log2(e)|1.44269504088896340736|
|M_LOG10E|LOG10(e)|0.434294481903251827651|
|M_LN2|ln(2)|0.693147180559945309417|
|M_LN10|ln(10)|2.30258509299404568402|
|M_PI|Pi|3.14159265358979323846|
|M_PI_2|Pi/2|1.57079632679489661923|
|M_PI_4|pi/4|0.785398163397448309616|
|M_1_PI|1/pi|0.318309886183790671538|
|M_2_PI|2/pi|0.636619772367581343076|
|M_2_SQRTPI|2/SQRT(pi)|1.12837916709551257390|
|M_SQRT2|SQRT(2)|1.41421356237309504880|
|M_SQRT1_2|1/SQRT(2)|0.707106781186547524401|

Stałe matematyczne nie są zdefiniowane w standardowe C/C++. Aby korzystać z nich, należy najpierw zdefiniować `_USE_MATH_DEFINES` , a następnie dołącz cmath lub math.h.

Plik ATLComTime.h obejmuje math.h, gdy projekt został skompilowany w trybie wydania. Użycie co najmniej jeden stałe matematyczne w projekcie, który obejmuje również ATLComTime.h, należy zdefiniować `_USE_MATH_DEFINES` przed wprowadzeniem ATLComTime.h.

## <a name="see-also"></a>Zobacz też

[Stałe globalne](../c-runtime-library/global-constants.md)