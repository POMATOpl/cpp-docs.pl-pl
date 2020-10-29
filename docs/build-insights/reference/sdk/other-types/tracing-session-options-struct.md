---
title: Struktura TRACING_SESSION_OPTIONS
description: Dowiedz się więcej o zestawie SDK usługi Build Insights dla programu C++ TRACING_SESSION_OPTIONS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3147debbfe1ea7ab4bcb4fa3bb8a803e66163557
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922393"
---
# <a name="tracing_session_options-structure"></a>Struktura TRACING_SESSION_OPTIONS

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_OPTIONS`Struktura jest używana podczas inicjowania struktury [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) lub [RELOG_DESCRIPTOR](relog-descriptor-struct.md) . Opisuje zdarzenia, które mają być przechwytywane podczas zbierania śladu.

## <a name="syntax"></a>Składnia

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `SystemEventFlags` | Maska bitów opisująca zdarzenia systemowe do przechwycenia. Aby uzyskać więcej informacji, zobacz [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md). |
| `MsvcEventFlags` | Maska bitów opisująca zdarzenia MSVC do przechwycenia. Aby uzyskać więcej informacji, zobacz [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md). |

::: moniker-end
