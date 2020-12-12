---
description: 'Dowiedz się więcej o: stałych akcji sygnałów'
title: Stałe akcji sygnałów
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: 380fed21b097b674958c6e2aae2f6b8c53845943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276988"
---
# <a name="signal-action-constants"></a>Stałe akcji sygnałów

Akcja podejmowana po odebraniu sygnału przerwania zależy od wartości `func` .

## <a name="syntax"></a>Składnia

```
#include <signal.h>
```

## <a name="remarks"></a>Uwagi

`func`Argument musi być adresem funkcji lub jedną ze stałych manifestu wymienionych poniżej i zdefiniowanym w sygnale. H.

|Stała|Opis|
|-|-|
| `SIG_DFL`  | Używa domyślnej odpowiedzi systemowej. Jeśli program wywołujący korzysta ze strumienia we/wy, bufory utworzone przez bibliotekę wykonawczą nie są opróżniane.  |
| `SIG_IGN`  | Ignoruje sygnał przerwania. Ta wartość nigdy nie powinna być określona `SIGFPE` , ponieważ stan zmiennoprzecinkowy procesu jest niezdefiniowany.  |
| `SIG_SGE`  | Wskazuje, że w sygnale Wystąpił błąd.  |
| `SIG_ACK`  | Wskazuje, że Odebrano potwierdzenie.  |
| `SIG_ERR`  | Wystąpił zwracany typ z sygnału wskazującego na błąd.  |

## <a name="see-also"></a>Zobacz też

[sygnał](../c-runtime-library/reference/signal.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
