---
description: 'Dowiedz się więcej o: makro InspectableClass'
title: InspectableClass — Makro
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: cb19db7f35e7bda351cd84fa4dcf1f6a2b2ea2ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229005"
---
# <a name="inspectableclass-macro"></a>InspectableClass — Makro

Ustawia nazwę klasy środowiska uruchomieniowego i poziom zaufania.

## <a name="syntax"></a>Składnia

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>Parametry

*runtimeClassName*<br/>
Pełna nazwa tekstowa klasy środowiska uruchomieniowego.

*trustLevel*<br/>
Jedna z [TrustLevel](/windows/win32/api/inspectable/ne-inspectable-trustlevel) wartości.

## <a name="remarks"></a>Uwagi

Makro **InspectableClass** może być używane tylko z typami środowisko wykonawcze systemu Windows.

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Klasa RuntimeClass](runtimeclass-class.md)
