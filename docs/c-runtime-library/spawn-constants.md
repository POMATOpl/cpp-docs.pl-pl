---
description: 'Dowiedz się więcej o: stałych tarła'
title: spawn — Stałe
ms.date: 11/04/2016
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
ms.openlocfilehash: 0bac30346c974fa63d65da78a097cb24768cb313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276962"
---
# <a name="spawn-constants"></a>spawn — Stałe

## <a name="syntax"></a>Składnia

```
#include <process.h>
```

## <a name="remarks"></a>Uwagi

`mode`Argument określa akcję wykonywaną przez proces wywołujący przed i podczas operacji duplikowania. Dostępne są następujące wartości `mode` :

|Stała|Znaczenie|
|--------------|-------------|
|`_P_OVERLAY`|Nakłada proces wywoływania z nowym procesem, niszczy proces wywołujący (ten sam efekt jak `_exec` wywołania).|
|`_P_WAIT`|Wstrzymuje wywoływanie wątku do momentu wykonania nowego procesu (synchronicznego `_spawn` ).|
|`_P_NOWAIT`, `_P_NOWAITO`|Kontynuuje wykonywanie procesu wywołującego współbieżnie z nowym procesem (asynchronicznym `_spawn` ).|
|`_P_DETACH`|Kontynuuje wykonywanie procesu wywołującego; nowy proces jest uruchamiany w tle bez dostępu do konsoli lub klawiatury. Wywołania `_cwait` względem nowego procesu zakończą się niepowodzeniem. Jest to asynchroniczny `_spawn` .|

## <a name="see-also"></a>Zobacz też

[_spawn, funkcje _wspawn](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
