---
title: Klasa zmiennych środowiskowych
description: Odwołanie do klasy zmiennych środowiskowych zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f707ab744aaf6097975ba9e189815df3c9f32266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920766"
---
# <a name="environmentvariable-class"></a>Klasa zmiennych środowiskowych

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`EnvironmentVariable`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) .

## <a name="syntax"></a>Składnia

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [SimpleEvent](simple-event.md) `EnvironmentVariable` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>Funkcje

[Nazwa](#name) 
 [Wartość](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a> Zmiennych środowiskowych

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) .

## <a name="name"></a><a name="name"></a> Nazwij

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa zmiennej środowiskowej.

## <a name="value"></a><a name="value"></a> Wartościami

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość zmiennej środowiskowej.

::: moniker-end
