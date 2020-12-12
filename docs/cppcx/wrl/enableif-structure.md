---
description: Dowiedz się więcej o strukturze EnableIf —
title: EnableIf — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 098dd5fdc7e37a7754d7124eba3e146575c127be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272854"
---
# <a name="enableif-structure"></a>EnableIf — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ.

*b*<br/>
Wyrażenie logiczne.

## <a name="remarks"></a>Uwagi

Definiuje element członkowski danych typu określonego przez drugi parametr szablonu, jeśli pierwszy parametr szablonu daje w wyniku **`true`** .

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`type`|Jeśli parametr szablonu *b* szacuje się na **`true`** , Częściowa specjalizacja definiuje element członkowski danych `type` jako typ `T` .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`EnableIf`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Internal. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
