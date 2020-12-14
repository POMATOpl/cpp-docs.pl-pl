---
description: 'Dowiedz się więcej o: FactoryCacheFlags Enumeration'
title: FactoryCacheFlags — Wyliczenie
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 68a86049bf1f6287a84ae4df2e27dbe3c63c91c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198508"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags — Wyliczenie

Określa, czy obiekty fabryki są buforowane.

## <a name="syntax"></a>Składnia

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Uwagi

Domyślnie zasady buforowania fabryki są określane jako parametr szablonu [ModuleType](moduletype-enumeration.md) podczas tworzenia obiektu [modułu](module-class.md) . Aby zastąpić te zasady, określ wartość **FactoryCacheFlags** podczas tworzenia obiektu fabryki.

| Zasady | Opis |
|-|-|
|`FactoryCacheDefault`|`Module`Używane są zasady buforowania obiektu.|
|`FactoryCacheEnabled`|Włącza buforowanie fabryki niezależnie od `ModuleType` parametru szablonu, który jest używany do tworzenia `Module` obiektu.|
|`FactoryCacheDisabled`|Wyłącza buforowanie fabryki niezależnie od `ModuleType` parametru szablonu, który jest używany do tworzenia `Module` obiektu.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
