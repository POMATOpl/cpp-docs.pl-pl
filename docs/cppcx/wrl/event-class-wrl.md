---
description: Dowiedz się więcej o klasie Event (WRL)
title: Event — Klasa (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: e3a61a40d1160830df80a7e0650e60fbf803e3d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272828"
---
# <a name="event-class-wrl"></a>Event — Klasa (WRL)

Reprezentuje zdarzenie.

## <a name="syntax"></a>Składnia

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                   | Opis
---------------------- | ------------------------------------------------
[Event:: Event](#event) | Inicjuje nowe wystąpienie klasy `Event`.

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                 | Opis
------------------------------------ | ------------------------------------------------------------------------
[Event:: operator =](#operator-assign) | Przypisuje określone `Event` odwołanie do bieżącego `Event` wystąpienia.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`HandleT`

`Event`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="eventevent"></a><a name="event"></a> Event:: Event

Inicjuje nowe wystąpienie klasy `Event`.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście do zdarzenia. Domyślnie *h* jest inicjowana do **`nullptr`** .

## <a name="eventoperator"></a><a name="operator-assign"></a> Event:: operator =

Przypisuje określone `Event` odwołanie do bieżącego `Event` wystąpienia.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Odwołanie rvalue do `Event` wystąpienia.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do bieżącego `Event` wystąpienia.
