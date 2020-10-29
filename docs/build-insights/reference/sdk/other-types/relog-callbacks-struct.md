---
title: Struktura RELOG_CALLBACKS
description: Informacje o strukturze RELOG_CALLBACKS zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b3beb656aa72ce4c8519c56c4c8bf6ca6577cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919802"
---
# <a name="relog_callbacks-structure"></a>Struktura RELOG_CALLBACKS

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_CALLBACKS`Struktura jest używana podczas inicjowania obiektu [RELOG_DESCRIPTOR](relog-descriptor-struct.md) . Określa funkcje, które mają być wywoływane podczas rejestrowania śledzenia zdarzeń systemu Windows (ETW).

## <a name="syntax"></a>Składnia

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `OnStartActivity` | Wywołuje się, by przetworzyć zdarzenie uruchomienia działania. |
| `OnStopActivity` | Wywołuje się, by przetworzyć zdarzenie zatrzymania działania. |
| `OnSimpleEvent` | Wywołuje się, by przetworzyć zdarzenie proste. |
| `OnTraceInfo` | Wywoływana raz na początku przebiegu ponownie rejestrowania po `OnBeginReloggingPass` wywołaniu. |
| `OnBeginRelogging` | Wywołuje się, gdy rozpocznie się sesja ponowna rejestracja przed rozpoczęciem przebiegu rejestrowania. |
| `OnEndRelogging` | Wywołuje się, gdy kończy się sesja po zakończeniu rejestracji, po zakończeniu przebiegu rejestrowania. |
| `OnBeginReloggingPass` | Wywołuje się, gdy rozpoczyna się ponowny rejestrowanie przed przetwarzaniem dowolnego zdarzenia. |
| `OnEndReloggingPass` | Wywołuje się, gdy kończy się rejestrowanie przebiegu, po przetworzeniu wszystkich zdarzeń. |

## <a name="remarks"></a>Uwagi

Wszystkie elementy członkowskie `RELOG_CALLBACKS` struktury muszą wskazywać na prawidłową funkcję. Aby uzyskać więcej informacji na temat zaakceptowanych podpisów funkcji, zobacz [OnRelogEventFunc](on-relog-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md)i [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
