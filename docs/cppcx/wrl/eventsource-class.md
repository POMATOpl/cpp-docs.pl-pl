---
description: Dowiedz się więcej o klasie EventSource
title: EventSource — Klasa
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: 2553d82a0fc16cd759f43ef2e4ae9527884cab10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272815"
---
# <a name="eventsource-class"></a>EventSource — Klasa

Reprezentuje zdarzenie inne niż Agile. `EventSource` funkcje elementów członkowskich Dodaj, Usuń i Wywołaj procedury obsługi zdarzeń. Dla zdarzeń Agile Użyj [AgileEventSource](agileeventsource-class.md).

## <a name="syntax"></a>Składnia

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Parametry

*TDelegateInterface*<br/>
Interfejs do delegata, który reprezentuje procedurę obsługi zdarzeń.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

| Nazwa                                     | Opis                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource:: EventSource](#eventsource) | Inicjuje nowe wystąpienie klasy `EventSource`. |

### <a name="public-methods"></a>Metody publiczne

| Nazwa                                 | Opis                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: Add](#add)             | Dołącza obsługę zdarzeń reprezentowane przez określony interfejs delegata do zestawu obsługi zdarzeń dla bieżącego `EventSource` obiektu.                     |
| [EventSource:: GetSize](#getsize)     | Pobiera liczbę programów obsługi zdarzeń skojarzonych z bieżącym `EventSource` obiektem.                                                                         |
| [EventSource:: InvokeAll —](#invokeall) | Wywołuje każdy program obsługi zdarzeń skojarzony z bieżącym `EventSource` obiektem przy użyciu określonych typów argumentów i argumentów.                                      |
| [EventSource:: Remove](#remove)       | Usuwa procedurę obsługi zdarzeń reprezentowaną przez określony token rejestracji zdarzeń z zestawu programów obsługi zdarzeń skojarzonych z bieżącym `EventSource` obiektem. |

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

| Nazwa                                                    | Opis                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: addRemoveLock_](#addremovelock)           | Synchronizuje dostęp do tablicy [targets_](#targets) podczas dodawania, usuwania lub wywoływania programów obsługi zdarzeń.                          |
| [EventSource:: targets_](#targets)                       | Tablica co najmniej jednego programu obsługi zdarzeń.                                                                                           |
| [EventSource:: targetsPointerLock_](#targetspointerlock) | Synchronizuje dostęp do wewnętrznych elementów członkowskich danych, nawet gdy programy obsługi zdarzeń dla tego elementu EventSource są dodawane, usuwane lub wywoływane. |

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`EventSource`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="eventsourceadd"></a><a name="add"></a> EventSource:: Add

Dołącza obsługę zdarzeń reprezentowane przez określony interfejs delegata do zestawu obsługi zdarzeń dla bieżącego `EventSource` obiektu.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametry

*delegateInterface*<br/>
Interfejs do obiektu delegata, który reprezentuje procedurę obsługi zdarzeń.

*klucza*<br/>
Po zakończeniu tej operacji, dojście, które reprezentuje zdarzenie. Użyj tego tokenu jako parametru do metody [Remove ()](#remove) , aby odrzucić procedurę obsługi zdarzeń.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="eventsourceaddremovelock_"></a><a name="addremovelock"></a> EventSource:: addRemoveLock_

Synchronizuje dostęp do tablicy [targets_](#targets) podczas dodawania, usuwania lub wywoływania programów obsługi zdarzeń.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsourceeventsource"></a><a name="eventsource"></a> EventSource:: EventSource

Inicjuje nowe wystąpienie klasy `EventSource`.

```cpp
EventSource();
```

## <a name="eventsourcegetsize"></a><a name="getsize"></a> EventSource:: GetSize

Pobiera liczbę programów obsługi zdarzeń skojarzonych z bieżącym `EventSource` obiektem.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba programów obsługi zdarzeń w [targets_](#targets).

## <a name="eventsourceinvokeall"></a><a name="invokeall"></a> EventSource:: InvokeAll —

Wywołuje każdy program obsługi zdarzeń skojarzony z bieżącym `EventSource` obiektem przy użyciu określonych typów argumentów i argumentów.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Parametry

*T0*<br/>
Typ argumentu obsługi zdarzeń zerowego.

*T1*<br/>
Typ pierwszego argumentu procedury obsługi zdarzeń.

*T2*<br/>
Typ drugiego argumentu procedury obsługi zdarzeń.

*T3*<br/>
Typ trzeciego argumentu procedury obsługi zdarzeń.

*T4*<br/>
Typ czwartego argumentu procedury obsługi zdarzeń.

*Otrzymując*<br/>
Typ piątego argumentu procedury obsługi zdarzeń.

*T6*<br/>
Typ szóstego argumentu procedury obsługi zdarzeń.

*T7*<br/>
Typ siódmego argumentu procedury obsługi zdarzeń.

*T8*<br/>
Typ argumentu programu obsługi zdarzeń ósmego.

*T9*<br/>
Typ dziewiątego argumentu procedury obsługi zdarzeń.

*arg0*<br/>
Argument programu obsługi zdarzeń zerowego.

*arg1*<br/>
Pierwszy argument programu obsługi zdarzeń.

*arg2*<br/>
Drugi argument programu obsługi zdarzeń.

*arg3*<br/>
Trzeci argument programu obsługi zdarzeń.

*arg4*<br/>
Czwarty argument procedury obsługi zdarzeń.

*arg5*<br/>
Piąty argument procedury obsługi zdarzeń.

*arg6*<br/>
Szósty argument procedury obsługi zdarzeń.

*arg7*<br/>
Siódmy argument obsługi zdarzeń.

*arg8*<br/>
Ósmy argument obsługi zdarzeń.

*arg9*<br/>
Dziewiąty argument obsługi zdarzeń.

## <a name="eventsourceremove"></a><a name="remove"></a> EventSource:: Remove

Usuwa procedurę obsługi zdarzeń reprezentowaną przez określony token rejestracji zdarzeń z zestawu programów obsługi zdarzeń skojarzonych z bieżącym `EventSource` obiektem.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Parametry

*klucza*<br/>
Dojście, które reprezentuje procedurę obsługi zdarzeń. Ten token został zwrócony, gdy program obsługi zdarzeń został zarejestrowany przez metodę [Add ()](#add) .

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat `EventRegistrationToken` struktury, zobacz temat **struktura systemu Windows:: Foundation:: EventRegistrationToken** w dokumentacji referencyjnej **środowisko wykonawcze systemu Windows** .

## <a name="eventsourcetargets_"></a><a name="targets"></a> EventSource:: targets_

Tablica co najmniej jednego programu obsługi zdarzeń.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Uwagi

Gdy wystąpi zdarzenie reprezentowane przez bieżący `EventSource` obiekt, procedury obsługi zdarzeń są wywoływane.

## <a name="eventsourcetargetspointerlock_"></a><a name="targetspointerlock"></a> EventSource:: targetsPointerLock_

Synchronizuje dostęp do wewnętrznych elementów członkowskich danych, nawet gdy programy obsługi zdarzeń `EventSource` są dodawane, usuwane lub wywoływane.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
