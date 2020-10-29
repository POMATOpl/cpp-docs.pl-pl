---
title: Klasa wywołania
description: Odwołanie do klasy wywołania zestawu SDK w usłudze C++ build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dfd463c7b9ca72dc14ad74b3759fdd1e3730d5a9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923147"
---
# <a name="invocation-class"></a>Klasa wywołania

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Invocation`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować do [kompilatora](../event-table.md#compiler) lub [konsolidatora](../event-table.md#linker) zdarzenia.

## <a name="syntax"></a>Składnia

```cpp
class Invocation : public Activity
{
    const INVOCATION_DATA* data_;

public:
    enum class Type
    {
        CL      = MSVC_TOOL_CODE_CL,
        LINK    = MSVC_TOOL_CODE_LINK
    };

    Invocation(const RawEvent& event);

    Type             Type() const;
    const char*      ToolVersionString() const;
    const wchar_t*   WorkingDirectory() const;
    const wchar_t*   ToolPath() const;

    const INVOCATION_VERSION_DATA& ToolVersion() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `Invocation` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[Invocation](#invocation)

### <a name="functions"></a>Funkcje

[Toolpath](#tool-path) 
 [ToolVersion](#tool-version) 
 [ToolVersionString](#tool-version-string) 
 [Typ](#type) 
 [WorkingDirectory](#working-directory)

## <a name="invocation"></a><a name="invocation"></a> Wywołania

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [kompilatora](../event-table.md#compiler) lub [konsolidatora](../event-table.md#linker) .

## <a name="toolpath"></a><a name="tool-path"></a> ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Wartość zwracana

Ścieżka bezwzględna do wywoływanego narzędzia.

## <a name="toolversion"></a><a name="tool-version"></a> ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Wartość zwracana

Wersja narzędzia, która została wywołana jako odwołanie [INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) .

## <a name="toolversionstring"></a><a name="tool-version-string"></a> ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Wartość zwracana

Wersja narzędzia, która została wywołana jako ciąg ANSI.

## <a name="type"></a><a name="type"></a> Wprowadź

```cpp
Type Type() const;
```

### <a name="return-value"></a>Wartość zwracana

Kod wskazujący narzędzie, które zostało wywołane.

## <a name="workingdirectory"></a><a name="working-directory"></a> WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Wartość zwracana

Ścieżka bezwzględna do katalogu, w którym wywołano narzędzie.

::: moniker-end
