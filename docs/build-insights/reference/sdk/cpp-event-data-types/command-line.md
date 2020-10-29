---
title: CommandLine — Klasa
description: Odwołanie do klasy wiersza polecenia zestawu SDK kompilacji w usłudze C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5214f2970329510088184dc3092db66607f4d67e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923330"
---
# <a name="commandline-class"></a>CommandLine — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`CommandLine`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [COMMAND_LINE](../event-table.md#command-line) .

## <a name="syntax"></a>Składnia

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [SimpleEvent](simple-event.md) `CommandLine` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[CommandLine](#command-line)

### <a name="functions"></a>Funkcje

[Wartość](#value)

## <a name="commandline"></a><a name="command-line"></a> Wiersza polecenia

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [COMMAND_LINE](../event-table.md#command-line) .

## <a name="value"></a><a name="value"></a> Wartościami

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Wartość zwracana

Ciąg zawierający wiersz polecenia. Wartość zawiera argumenty uzyskane z pliku odpowiedzi i ze zmiennych środowiskowych, takich jak CL, \_ CL \_ , link i \_ link \_ .

::: moniker-end
