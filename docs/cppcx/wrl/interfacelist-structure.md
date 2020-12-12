---
description: Dowiedz się więcej o strukturze InterfaceList —
title: InterfaceList — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 660ae5137b7ff41129ce3866f0d289045f7dee9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124582"
---
# <a name="interfacelist-structure"></a>InterfaceList — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Nazwa interfejsu; Pierwszy interfejs na liście cyklicznej.

*U*<br/>
Nazwa interfejsu; Pozostałe interfejsy na liście cyklicznej.

## <a name="remarks"></a>Uwagi

Służy do tworzenia cyklicznej listy interfejsów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`FirstT`|Synonim dla parametru szablonu *T*.|
|`RestT`|Synonim dla parametru szablonu *U*.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`InterfaceList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
