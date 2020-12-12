---
description: 'Dowiedz się więcej o: makra ActivatableClass'
title: ActivatableClass Makra
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 2b59101373de72ca88338750bb7fe9169376ac65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287947"
---
# <a name="activatableclass-macros"></a>ActivatableClass Makra

Wypełnia wewnętrzną pamięć podręczną, która zawiera fabrykę, która może utworzyć wystąpienie określonej klasy.

## <a name="syntax"></a>Składnia

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>Parametry

*Nazwą*<br/>
Nazwa klasy do utworzenia.

*indywidual*<br/>
Fabryka, która utworzy wystąpienie określonej klasy.

*serverName*<br/>
Nazwa, która określa podzbiór fabryk w module.

## <a name="remarks"></a>Uwagi

Nie używaj tych makr z klasycznym modelem COM, chyba że używasz `#undef` dyrektywy do upewnienia się, że `__WRL_WINRT_STRICT__` Definicja makra zostanie usunięta.

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Klasa modułu](module-class.md)
