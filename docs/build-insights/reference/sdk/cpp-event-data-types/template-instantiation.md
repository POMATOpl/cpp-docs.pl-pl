---
title: Klasa TemplateInstantiation
description: Odwołanie do klasy TemplateInstantiation zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7ff03aaa431f5c5e217f605698a255686411b479
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920440"
---
# <a name="templateinstantiation-class"></a>Klasa TemplateInstantiation

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiation`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

## <a name="syntax"></a>Składnia

```cpp
class TemplateInstantiation : public Activity
{
public:
    enum class Kind
    {
        CLASS       = TEMPLATE_INSTANTIATION_KIND_CODE_CLASS,
        FUNCTION    = TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION,
        VARIABLE    = TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE,
        CONCEPT     = TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT
    };

    TemplateInstantiation(const RawEvent& event);

    const unsigned long long& SpecializationSymbolKey() const;
    const unsigned long long& PrimaryTemplateSymbolKey() const;

    Kind Kind() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `TemplateInstantiation` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[TemplateInstantiation](#template-instantiation)

### <a name="functions"></a>Funkcje

[Rodzaj](#kind) 
 [PrimaryTemplateSymbolKey](#primary-template-symbol-key) 
 [SpecializationSymbolKey](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a> Natur

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Wartość zwracana

Kod opisujący typ tworzenia wystąpienia szablonu, który został wykonany.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a> PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator liczbowy typu szablonu, który był wyspecjalizowany. Ten identyfikator jest unikatowy w ramach przebiegu frontonu kompilatora.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a> SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator liczbowy typu specjalizacji. Ten identyfikator jest unikatowy w ramach przebiegu frontonu kompilatora.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a> TemplateInstantiation

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

::: moniker-end
