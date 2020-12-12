---
description: Dowiedz się więcej o strukturze ArgTraitsHelper
title: ArgTraitsHelper — Struktura
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: a749c48c72c837eb0898d32ddd08410b87918871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175862"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parametry

*TDelegateInterface*<br/>
Interfejs delegata.

## <a name="remarks"></a>Uwagi

Ułatwia definiowanie typowych cech argumentów delegatów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa         | Opis
------------ | ------------------------------------------------------
`methodType` | Synonim dla `decltype(&TDelegateInterface::Invoke)` .
`Traits`     | Synonim dla `ArgTraits<methodType>` .

### <a name="public-constants"></a>Stałe publiczne

Nazwa                           | Opis
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper:: args](#args) | Pomaga [ArgTraits:: args](#args) , aby zachować liczbę parametrów `Invoke` metody interfejsu delegata.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ArgTraitsHelper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="argtraitshelperargs"></a><a name="args"></a> ArgTraitsHelper:: args

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Uwagi

Pomaga `ArgTraitsHelper::args` zachować liczbę parametrów `Invoke` metody interfejsu delegata.
