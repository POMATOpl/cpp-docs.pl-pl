---
title: Stałe TRACING_SESSION_MSVC_EVENT_FLAGS
description: Zestaw SDK w usłudze C++ build Insights TRACING_SESSION_MSVC_EVENT_FLAGS informacje stałe.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_MSVC_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 78762001d4a8b5d36bb9e8fa6b6ed03cd59450a5
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919731"
---
# <a name="tracing_session_msvc_event_flags-constants"></a>Stałe TRACING_SESSION_MSVC_EVENT_FLAGS

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_MSVC_EVENT_FLAGS`Stałe są używane do opisywania, które zdarzenia MSVC mają być zbierane podczas śledzenia. Użyj ich, aby zainicjować [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) pole struktury TRACING_SESSION_OPTIONS `MsvcEventFlags` .

## <a name="syntax"></a>Składnia

```cpp
static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_BASIC                                = 0x0001ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_FILES                       = 0x0004ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_TEMPLATE_INSTANTIATIONS     = 0x0008ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_BACKEND_FUNCTIONS                    = 0x1000ULL;

static const unsigned long long
    TRACING_SESSION_MSVC_EVENT_FLAGS_ALL                                  = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Zdarzenia włączone przez tę flagę |
|--|--|
| `TRACING_SESSION_MSVC_EVENT_FLAGS_BASIC` | Ta flaga jest skojarzona z poniższymi zdarzeniami. Jest ona uaktywniana domyślnie przez zestaw SDK usługi Build Insights, nawet jeśli nie zostanie określona jawnie. Nie można wyłączyć tych zdarzeń.<br/><br/>[BACK_END_PASS](../event-table.md#back-end-pass)[BOTTOM_UP](../event-table.md#bottom-up)<br/>[C1_DLL](../event-table.md#c1-dll)<br/>[C2_DLL](../event-table.md#c2-dll)<br/>[CODE_GENERATION](../event-table.md#code-generation)<br/>[COMMAND_LINE](../event-table.md#command-line)<br/>[COMPILER](../event-table.md#compiler)<br/>[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)<br/>[EXP_OUTPUT](../event-table.md#exp-output)<br/>[FILE_INPUT](../event-table.md#file-input)<br/>[FRONT_END_PASS](../event-table.md#front-end-pass)<br/>[FRONT_END_PASS](../event-table.md#front-end-pass)<br/>[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)<br/>[LIB_OUTPUT](../event-table.md#lib-output)<br/>[KONSOLIDATORA](../event-table.md#linker)<br/>[LTCG](../event-table.md#ltcg)<br/>[OBJ_OUTPUT](../event-table.md#obj-output)<br/>[OPT_ICF](../event-table.md#opt-icf)<br/>[OPT_LBR](../event-table.md#opt-lbr)<br/>[OPT_REF](../event-table.md#opt-ref)<br/>[PASS1](../event-table.md#pass1)<br/>[PASS2](../event-table.md#pass2)<br/>[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref)<br/>[NICI](../event-table.md#thread)<br/>[TOP_DOWN](../event-table.md#top-down)<br/>[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_FILES` | [FRONT_END_FILE](../event-table.md#front-end-file) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_FRONTEND_TEMPLATE_INSTANTIATIONS` | [SYMBOL_NAME](../event-table.md#symbol-name)<br/>[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_BACKEND_FUNCTIONS` | [FORCE_INLINEE](../event-table.md#force-inlinee)<br/>[FUNKCYJN](../event-table.md#function) |
| `TRACING_SESSION_MSVC_EVENT_FLAGS_ALL` | Ta flaga włącza wszystkie zdarzenia. |

::: moniker-end
