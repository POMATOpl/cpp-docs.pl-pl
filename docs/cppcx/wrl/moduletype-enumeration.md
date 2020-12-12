---
description: 'Dowiedz się więcej o: ModuleType Enumeration'
title: ModuleType — Wyliczenie
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 148f9594fd16a6c8a2af70ac0ff2ac03cd1f62e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209376"
---
# <a name="moduletype-enumeration"></a>ModuleType — Wyliczenie

Określa, czy moduł powinien obsługiwać serwer w toku, czy też poza procesem.

## <a name="syntax"></a>Składnia

```cpp
enum ModuleType;
```

## <a name="members"></a>Elementy członkowskie

### <a name="values"></a>Wartości

|Nazwa|Opis|
|----------|-----------------|
|`InProc`|Serwer w procesie.|
|`OutOfProc`|Serwer poza procesem.|
|`DisableCaching`|Wyłącz mechanizm buforowania w module.|
|`InProcDisableCaching`|Kombinacja `InProc` i `DisableCaching` .|
|`OutOfProcDisableCaching`|Kombinacja `OutOfProc` i `DisableCaching` .|

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
