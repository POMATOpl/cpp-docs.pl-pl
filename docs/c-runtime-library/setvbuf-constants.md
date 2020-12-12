---
description: 'Dowiedz się więcej o: setvbuf — stałych'
title: setvbuf — Stałe
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 375c692f4437bd60c84e37c857e078d9386ffb1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277014"
---
# <a name="setvbuf-constants"></a>setvbuf — Stałe

## <a name="syntax"></a>Składnia

```
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Te stałe reprezentują typ bufora dla `setvbuf` .

Możliwe wartości są określone przez następujące stałe manifestu:

|Stała|Znaczenie|
|--------------|-------------|
|`_IOFBF`|Pełne buforowanie: bufor określony w wywołaniu `setvbuf` jest używany, a jego rozmiar jest określony w `setvbuf` wywołaniu. Jeśli wskaźnik buforu ma **wartość null**, używany jest automatycznie przydzielony bufor o określonym rozmiarze.|
|`_IOLBF`|Analogicznie jak `_IOFBF` .|
|`_IONBF`|Nie jest używany żaden bufor, niezależnie od argumentów w wywołaniu `setvbuf` .|

## <a name="see-also"></a>Zobacz też

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
