---
title: Stałe TRACING_SESSION_SYSTEM_EVENT_FLAGS
description: Zestaw SDK w usłudze C++ build Insights TRACING_SESSION_SYSTEM_EVENT_FLAGS informacje stałe.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 346c955355ffbc6c062a34bf928f16ccd3940154
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922374"
---
# <a name="tracing_session_system_event_flags-constants"></a>Stałe TRACING_SESSION_SYSTEM_EVENT_FLAGS

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS`Stałe są używane do opisywania, które zdarzenia systemowe należy zebrać podczas śledzenia. Użyj ich, aby zainicjować [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) pole struktury TRACING_SESSION_OPTIONS `SystemEventFlags` .

## <a name="syntax"></a>Składnia

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Zdarzenia włączone przez tę flagę |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | Ta flaga jest uaktywniana domyślnie przez zestaw SDK języka C++ build Insights, nawet jeśli nie została określona jawnie. Umożliwia ona podstawowe zdarzenia systemowe, które są wymagane przez program C++ build Insights do prawidłowego działania. Zdarzenia włączone przez tę flagę zawierają informacje dotyczące procesów, wątków i ładowania obrazu. Nie można wyłączyć tych zdarzeń. |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Przykłady użycia procesora CPU |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | Ta flaga włącza wszystkie zdarzenia systemowe. |

::: moniker-end
