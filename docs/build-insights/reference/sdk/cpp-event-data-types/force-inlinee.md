---
title: Klasa ForceInlinee
description: Odwołanie do klasy ForceInlinee zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53fff7b6cfd37ba3e3211dd072c1ce3386d00fda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920674"
---
# <a name="forceinlinee-class"></a>Klasa ForceInlinee

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`ForceInlinee`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [FORCE_INLINEE](../event-table.md#force-inlinee) .

## <a name="syntax"></a>Składnia

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [SimpleEvent](simple-event.md) `ForceInlinee` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>Funkcje

[Nazwa](#name) 
 [Rozmiar](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a> ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [FORCE_INLINEE](../event-table.md#force-inlinee) .

## <a name="name"></a><a name="name"></a> Nazwij

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa funkcji wymuszonej, zakodowana w UTF-8.

## <a name="size"></a><a name="size"></a> Zmienia

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar funkcji bezwierszowej w postaci liczby instrukcji pośrednich.

::: moniker-end
