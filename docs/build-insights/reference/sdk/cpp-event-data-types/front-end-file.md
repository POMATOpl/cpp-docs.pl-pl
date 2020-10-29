---
title: Klasa FrontEndFile
description: Odwołanie do klasy FrontEndFile zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7715a153df538eab94b8de5281a91d4f6b439ff9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920661"
---
# <a name="frontendfile-class"></a>Klasa FrontEndFile

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFile`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [FRONT_END_FILE](../event-table.md#front-end-file) .

## <a name="syntax"></a>Składnia

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `FrontEndFile` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[FrontEndFile](#front-end-file)

### <a name="functions"></a>Funkcje

[Ścieżka](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a> FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [FRONT_END_FILE](../event-table.md#front-end-file) .

## <a name="path"></a><a name="path"></a> Ścieżka

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Wartość zwracana

Ścieżka bezwzględna do pliku zakodowana w formacie UTF-8.

::: moniker-end
