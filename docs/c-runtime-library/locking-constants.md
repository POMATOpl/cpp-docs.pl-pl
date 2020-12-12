---
description: 'Dowiedz się więcej o: _locking stałych'
title: _locking — Stałe
ms.date: 11/04/2016
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
ms.openlocfilehash: 143c1416dada19e0bd35f1607d77826d98817879
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331024"
---
# <a name="_locking-constants"></a>_locking — Stałe

## <a name="syntax"></a>Składnia

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Uwagi

Argument *mode* w wywołaniu `_locking` funkcji określa akcję blokowania, która ma zostać wykonana.

Argument *mode* musi być jednym z następujących stałych manifestu.

|Wartość|Opis|
|-|-|
| `_LK_LOCK`  | Blokuje określone bajty. Jeśli bajty nie mogą być zablokowane, funkcja próbuje ponownie po 1 sekundzie. Jeśli po 10 próbach nie będzie można zablokować bajtów, funkcja zwróci błąd.  |
| `_LK_RLCK`  | Analogicznie jak `_LK_LOCK` .  |
|`_LK_NBLCK`  | Blokuje określone bajty. Jeśli bajty nie mogą być zablokowane, funkcja zwraca błąd.  |
| `_LK_NBRLCK`  | Analogicznie jak `_LK_NBLCK` .  |
| `_LK_UNLCK`  | Odblokowuje określone bajty. (Bajty muszą być wcześniej zablokowane).  |

## <a name="see-also"></a>Zobacz też

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
