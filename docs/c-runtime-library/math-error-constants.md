---
description: 'Dowiedz się więcej o programie: stałe błędów matematycznych'
title: Stałe błędów matematycznych
ms.date: 11/04/2016
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
ms.openlocfilehash: e5f94f94a28543f0405cce57941a872c416d0c20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258749"
---
# <a name="math-error-constants"></a>Stałe błędów matematycznych

## <a name="syntax"></a>Składnia

```
#include <math.h>
```

## <a name="remarks"></a>Uwagi

Procedury matematyczne biblioteki wykonawczej mogą generować stałe błędów matematycznych.

Te błędy, opisane w poniższej kolejności, odpowiadają typom wyjątków zdefiniowanym w MATH. H i są zwracane przez `_matherr` funkcję w przypadku wystąpienia błędu matematycznego.

|Stała|Znaczenie|
|--------------|-------------|
|`_DOMAIN`|Argument funkcji jest poza domeną funkcji.|
|`_OVERFLOW`|Wynik jest za duży, aby można go było przedstawić w zwracanym typie funkcji.|
|`_PLOSS`|Wystąpiła częściowa utrata istotności.|
|`_SING`|Argument Singularity: argument funkcji ma niedozwoloną wartość. (Na przykład wartość 0 jest przenoszona do funkcji, która wymaga wartości niezerowej).|
|`_TLOSS`|Przekroczono łączną utratę istotności.|
|`_UNDERFLOW`|Wynik jest zbyt mały, aby można go było przedstawić.|

## <a name="see-also"></a>Zobacz też

[_matherr](../c-runtime-library/reference/matherr.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
