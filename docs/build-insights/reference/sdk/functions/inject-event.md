---
title: InjectEvent
description: Dokumentacja funkcji InjectEvent zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4d85f17a6d553d9dffa727824e6d4de94518645
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922846"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`InjectEvent`Funkcja jest wywoływana w ramach ponownego rejestrowania implementującego interfejs [IRelogger](../other-types/irelogger-class.md) . Służy do zapisywania zdarzenia śledzenia zdarzeń systemu Windows (ETW) w wyjściowym pliku śledzenia sesji ponownego rejestrowania.

## <a name="syntax"></a>Składnia

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>Parametry

*relogSession*\
Wskaźnik do sesji rejestrowania. Sesja ponownego rejestrowania jest udostępniana w celu ponownego wyrejestratora, który implementuje `IRelogger` interfejs. Aby uzyskać więcej informacji, zobacz [IRelogger](../other-types/irelogger-class.md).

*Identyfikatorem*\
Identyfikator GUID dostawcy śledzenia zdarzeń systemu Windows (ETW), w którym zdarzenie ETW zostanie zarejestrowane.

*eventDescriptor*\
Deskryptor zdarzenia ETW dla zdarzenia ETW, które jest rejestrowane.

*Identyfikator*\
Identyfikator procesu (PID) dla zdarzenia ETW, które jest rejestrowane ponownie.

*threadId*\
Identyfikator wątku (TID) dla zdarzenia ETW, które jest rejestrowane.

*processorIndex*\
Indeks procesora dla zdarzenia ETW, które jest rejestrowane ponownie.

*znacznik czasu*\
Sygnatura czasowa zdarzenia ETW, które jest rejestrowane.

*Data*\
Wskaźnik do danych, które powinny zostać uwzględnione w rejestrowanym zdarzeniu ETW.

*byteCount*\
Rozmiar danych (w bajtach) wskazywanych przez *dane* .

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat pojęć ETW, takich jak *Identyfikator GUID dostawcy* i *deskryptor zdarzenia* , zapoznaj się z [dokumentacją ETW](/windows/win32/etw/about-event-tracing). Aby uzyskać szczegółowe informacje na temat rozpoczynania sesji ponownego rejestrowania za pomocą zestawu SDK usługi kompilacja kompilacji w języku C++, zobacz [relog](relog.md).

::: moniker-end
