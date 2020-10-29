---
title: Event, Klasa
description: Odwołanie do klasy grupy zdarzeń SDK kompilacji usługi C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 57cbc7a053132909149aee182b9560e2ee33c161
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923316"
---
# <a name="eventgroup-class"></a>Event, Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`EventGroup`Szablon klasy jest klasą bazową dla wszystkich klas przechwytywania grup.

## <a name="syntax"></a>Składnia

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>Parametry

*TActivity* Typ działania zawarty w grupie.

## <a name="members"></a>Elementy członkowskie

### <a name="functions"></a>Funkcje

[Wstecz](#back) 
 [Rozpocznij](#begin) 
 [koniec](#end) 
 [Przód](#front) 
 [operator []](#subscript-operator) 
 [Rozmiar](#size)

## <a name="back"></a><a name="back"></a> Wstecz

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do ostatniego zdarzenia działania w grupie.

## <a name="begin"></a><a name="begin"></a> zaczną

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Wartość zwracana

Iterator wskazujący początek grupy zdarzeń działania.

## <a name="end"></a><a name="end"></a> punktów

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Wartość zwracana

Iterator wskazujący jedną pozycję poza końcem grupy zdarzeń działania.

## <a name="front"></a><a name="front"></a> FSB

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do pierwszego zdarzenia działania w grupie.

## <a name="operator"></a><a name="subscript-operator"></a> operator []

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Parametry

*indeks*\
Indeks elementu, do którego można uzyskać dostęp w grupie zdarzeń działania.

### <a name="return-value"></a>Wartość zwracana

Zdarzenie ze stosu zdarzeń przechowywane w pozycji wskazywanej przez *indeks* .

## <a name="size"></a><a name="size"></a> Zmienia

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar grupy zdarzeń.

::: moniker-end
