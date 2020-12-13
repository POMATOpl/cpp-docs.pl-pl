---
description: 'Dowiedz się więcej o: CancelTransitionPolicy Enumeration'
title: CancelTransitionPolicy — Wyliczenie
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: 8de995ed492f8f1260534b08b818b77d889d95fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344539"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy — Wyliczenie

Wskazuje, w jaki sposób operacja asynchroniczna przechodzi do stanu końcowego zakończone lub błąd powinien zachowywać się w odniesieniu do stanu anulowanego przez klienta.

## <a name="syntax"></a>Składnia

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Elementy członkowskie

### <a name="values"></a>Wartości

|Nazwa|Opis|
|----------|-----------------|
|`RemainCanceled`|Jeśli operacja asynchroniczna jest obecnie w stanie anulowania żądanym przez klienta, oznacza to, że pozostanie w stanie anulowanym w przeciwieństwie do przejścia do stanu zakończenia lub błędu terminalu.|
|`TransitionFromCanceled`|Jeśli operacja asynchroniczna jest obecnie w stanie anulowania żądanym przez klienta, oznacza to, że stan powinien przejść z tego stanu, aby stan został anulowany lub błąd został określony przez wywołanie, które wykorzystuje tę flagę.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** Async. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
