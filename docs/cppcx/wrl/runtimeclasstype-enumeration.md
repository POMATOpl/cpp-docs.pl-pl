---
description: 'Dowiedz się więcej o: RuntimeClassType — Enumeration'
title: RuntimeClassType — Wyliczenie
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 10055d79148124e886c4da50e40ffdb7d3d0fec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135281"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType — Wyliczenie

Określa typ wystąpienia [RuntimeClass](runtimeclass-class.md) , które jest obsługiwane.

## <a name="syntax"></a>Składnia

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Elementy członkowskie

### <a name="values"></a>Wartości

|Nazwa|Opis|
|----------|-----------------|
|`ClassicCom`|Klasyczna Klasa środowiska uruchomieniowego COM.|
|`Delegate`|Odpowiednik `ClassicCom` .|
|`InhibitFtmBase`|Wyłącza `FtmBase` obsługę, chociaż `__WRL_CONFIGURATION_LEGACY__` nie jest zdefiniowana.|
|`InhibitWeakReference`|Wyłącza obsługę słabej referencji.|
|`WinRt`|Klasa środowisko wykonawcze systemu Windows.|
|`WinRtClassicComMix`|Kombinacja `WinRt` i `ClassicCom` .|

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
