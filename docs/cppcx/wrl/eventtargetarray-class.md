---
description: 'Dowiedz się więcej na temat: Klasa EventTargetArray'
title: EventTargetArray — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: ac3199d2374a47e94705f8f51672bfedd0b7bf20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198586"
---
# <a name="eventtargetarray-class"></a>EventTargetArray — Klasa

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Uwagi

Reprezentuje tablicę obsługi zdarzeń.

Programy obsługi zdarzeń skojarzone z obiektem [EventSource](eventsource-class.md) są przechowywane w chronionych `EventTargetArray` elementach członkowskich danych.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                           | Opis
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray:: EventTargetArray](#eventtargetarray)        | Inicjuje nowe wystąpienie klasy `EventTargetArray`.
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | Deinicjalizuje bieżącą `EventTargetArray` klasę.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                  | Opis
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray:: AddTail](#addtail) | Dołącza określony program obsługi zdarzeń do końca wewnętrznej tablicy obsługi zdarzeń.
[EventTargetArray:: BEGIN](#begin)     | Pobiera adres pierwszego elementu w wewnętrznej tablicy obsługi zdarzeń.
[EventTargetArray:: end](#end)         | Pobiera adres ostatniego elementu w wewnętrznej tablicy obsługi zdarzeń.
[EventTargetArray:: length](#length)   | Pobiera bieżącą liczbę elementów w wewnętrznej tablicy obsługi zdarzeń.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`EventTargetArray`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a> EventTargetArray:: ~ EventTargetArray

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Uwagi

Deinicjalizuje bieżącą `EventTargetArray` klasę.

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a> EventTargetArray:: AddTail

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parametry

*postaci*<br/>
Wskaźnik do programu obsługi zdarzeń do dołączenia.

### <a name="remarks"></a>Uwagi

Dołącza określony program obsługi zdarzeń do końca wewnętrznej tablicy obsługi zdarzeń.

`AddTail()` jest przeznaczony do użytku wewnętrznego tylko przez `EventSource` klasę.

## <a name="eventtargetarraybegin"></a><a name="begin"></a> EventTargetArray:: BEGIN

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Wartość zwracana

Adres pierwszego elementu w wewnętrznej tablicy obsługi zdarzeń.

### <a name="remarks"></a>Uwagi

Pobiera adres pierwszego elementu w wewnętrznej tablicy obsługi zdarzeń.

## <a name="eventtargetarrayend"></a><a name="end"></a> EventTargetArray:: end

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Wartość zwracana

Adres ostatniego elementu w wewnętrznej tablicy obsługi zdarzeń.

### <a name="remarks"></a>Uwagi

Pobiera adres ostatniego elementu w wewnętrznej tablicy obsługi zdarzeń.

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a> EventTargetArray:: EventTargetArray

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parametry

*godz.*<br/>
Po wykonaniu tej operacji konstruktora parametr *HR* wskazuje, czy alokacja tablicy zakończyła się powodzeniem, czy niepowodzeniem. Na poniższej liście przedstawiono możliwe wartości dla elementu *HR*.

- S_OK<br/>
  Operacja zakończyła się pomyślnie.

- E_OUTOFMEMORY<br/>
  Nie można alokować pamięci dla tablicy.

- S_FALSE<br/>
  *Elementy* parametrów są mniejsze lub równe zeru.

*produktów*<br/>
Liczba elementów tablicy do przydzielenia.

### <a name="remarks"></a>Uwagi

Inicjuje nowe wystąpienie klasy `EventTargetArray`.

`EventTargetArray` służy do zachowywania tablicy programów obsługi zdarzeń w `EventSource` obiekcie.

## <a name="eventtargetarraylength"></a><a name="length"></a> EventTargetArray:: length

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
size_t Length();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca liczba elementów w wewnętrznej tablicy obsługi zdarzeń.

### <a name="remarks"></a>Uwagi

Pobiera bieżącą liczbę elementów w wewnętrznej tablicy obsługi zdarzeń.
