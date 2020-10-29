---
title: Klasa FileOutput
description: Odwołanie do klasy FileOutput zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 65e23715d8ac47a8653215e8bd3ee7a43bbe80a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923242"
---
# <a name="fileoutput-class"></a>Klasa FileOutput

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FileOutput`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)lub [OBJ_OUTPUT](../event-table.md#obj-output) zdarzenia.

## <a name="syntax"></a>Składnia

```cpp
class FileOutput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [SimpleEvent](simple-event.md) `FileOutput` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[FileOutput](#file-output)

### <a name="functions"></a>Funkcje

[Ścieżka](#path) 
 [Typ](#type)

## <a name="fileoutput"></a><a name="file-output"></a> FileOutput

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)lub [OBJ_OUTPUT](../event-table.md#obj-output) zdarzenia.

## <a name="path"></a><a name="path"></a> Ścieżka

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Wartość zwracana

Ścieżka bezwzględna do pliku wyjściowego.

## <a name="type"></a><a name="type"></a> Wprowadź

```cpp
Type Type() const;
```

### <a name="return-value"></a>Wartość zwracana

Kod opisujący typ pliku wyjściowego.

::: moniker-end
