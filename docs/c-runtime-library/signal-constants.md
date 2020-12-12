---
description: 'Dowiedz się więcej o: stałych sygnału'
title: sygnał — Stałe
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: 57615e3a694ae24c0bfefe42b6a8ddd1de2a55ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277001"
---
# <a name="signal-constants"></a>sygnał — Stałe

## <a name="syntax"></a>Składnia

```
#include <signal.h>
```

## <a name="remarks"></a>Uwagi

`sig`Argument musi być jednym z stałych manifestu wymienionych poniżej (zdefiniowane w sygnale). H).

|Stała|Opis|
|-|-|
|SIGABRT|Nietypowe zakończenie. Akcja domyślna kończy program wywołujący z kodem zakończenia 3.  |
|SIGABRT_COMPAT|Analogicznie jak SIGABRT. W celu zapewnienia zgodności z innymi platformami.  |
|SIGFPE|Błąd zmiennoprzecinkowy, taki jak Overflow, dzielenie przez zero lub Nieprawidłowa operacja. Akcja domyślna kończy program wywołujący.  |
|SIGILL|Niedozwolona instrukcja. Akcja domyślna kończy program wywołujący.  |
|SIGINT|CTRL + C przerwanie. Akcja domyślna kończy program wywołujący z kodem zakończenia 3.  |
|SIGSEGV|Niedozwolony dostęp do magazynu. Akcja domyślna kończy program wywołujący.  |
|SIGTERM|Żądanie zakończenia zostało wysłane do programu. Akcja domyślna kończy program wywołujący z kodem zakończenia 3.  |
|SIG_ERR|Wystąpił zwracany typ z sygnału wskazującego na błąd.  |

## <a name="see-also"></a>Zobacz też

[sygnał](../c-runtime-library/reference/signal.md)<br/>
[wywołaj](../c-runtime-library/reference/raise.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
