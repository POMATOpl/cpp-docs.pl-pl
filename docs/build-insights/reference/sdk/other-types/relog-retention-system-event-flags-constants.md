---
title: Stałe RELOG_RETENTION_SYSTEM_EVENT_FLAGS
description: Zestaw SDK w usłudze C++ build Insights RELOG_RETENTION_SYSTEM_EVENT_FLAGS informacje stałe.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e0144835568dab12c8593fe8fbfa820f6cde7647
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919737"
---
# <a name="relog_retention_system_event_flags-constants"></a>Stałe RELOG_RETENTION_SYSTEM_EVENT_FLAGS

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS`Stałe są używane do opisywania, które zdarzenia systemowe należy zachować w ponownie zarejestrowanym śledzeniu. Użyj ich, aby zainicjować [RELOG_DESCRIPTOR](relog-descriptor-struct.md) pole struktury RELOG_DESCRIPTOR `SystemEventsRetentionFlags` .

## <a name="syntax"></a>Składnia

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Zachowaj Przykładowe zdarzenia systemowe dotyczące procesora podczas ponownego rejestrowania śledzenia. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Zachowaj wszystkie zdarzenia systemowe w rejestrowanym śladzie. |

## <a name="remarks"></a>Uwagi

::: moniker-end
