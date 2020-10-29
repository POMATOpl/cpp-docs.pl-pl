---
title: Symbolname — Klasa
description: Odwołanie do klasy symboli SDK kompilacji usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a749d95b3812df8b1cc0cd7d2da037e98467cefc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920479"
---
# <a name="symbolname-class"></a>Symbolname — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`SymbolName`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [SYMBOL_NAME](../event-table.md#symbol-name) .

## <a name="syntax"></a>Składnia

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [SimpleEvent](simple-event.md) `SymbolName` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[SymbolName](#symbol-name)

### <a name="functions"></a>Funkcje

[Klucz](#key) 
 [Nazwa](#name)

## <a name="key"></a><a name="key"></a> Głównych

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator liczbowy typu reprezentowanego przez ten symbol. Ten identyfikator jest unikatowy w ramach przebiegu frontonu kompilatora.

## <a name="name"></a><a name="name"></a> Nazwij

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa typu reprezentowanego przez symbol zakodowana w UTF-8.

## <a name="symbolname"></a><a name="symbol-name"></a> Symbolname

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [SYMBOL_NAME](../event-table.md#symbol-name) .

::: moniker-end
