---
title: stałe przestrzeni nazw współbieżności
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::AgentEventGuid
- concrt/concurrency::COOPERATIVE_TIMEOUT_INFINITE
- concrt/concurrency::COOPERATIVE_WAIT_TIMEOUT
- concrt/concurrency::ConcRTEventGuid
- concrt/concurrency::ConcRT_ProviderGuid
- concrt/concurrency::INHERIT_THREAD_PRIORITY
- concrt/concurrency::LockEventGuid
- concrt/concurrency::PPLParallelForEventGuid
- concrt/concurrency::PPLParallelForeachEventGuid
- concrt/concurrency::ResourceManagerEventGuid
- concrt/concurrency::ScheduleGroupEventGuid
- concrt/concurrency::VirtualProcessorEventGuid
ms.assetid: 6f81fc4c-b10c-479e-8717-9c292360d5a0
ms.openlocfilehash: 6ddad8e4bc20be902332e1fd277d26b8d24b2ffd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326260"
---
# <a name="concurrency-namespace-constants"></a>stałe przestrzeni nazw współbieżności

||||
|-|-|-|
|[AgentEventGuid](#agenteventguid)|[CONCRT_RM_VERSION_1](#concrt_rm_version_1)|[COOPERATIVE_TIMEOUT_INFINITE](#cooperative_timeout_infinite)|
|[COOPERATIVE_WAIT_TIMEOUT](#cooperative_wait_timeout)|[ChoreEventGuid](#choreeventguid)|[ConcRTEventGuid](#concrteventguid)|
|[ConcRT_ProviderGuid](#concrt_providerguid)|[ContextEventGuid](#contexteventguid)|[INHERIT_THREAD_PRIORITY](#inherit_thread_priority)|
|[LockEventGuid](#lockeventguid)|[MaxExecutionResources](#maxexecutionresources)|[PPLParallelForEventGuid](#pplparallelforeventguid)|
|[PPLParallelForeachEventGuid](#pplparallelforeacheventguid)|[PPLParallelInvokeEventGuid](#pplparallelinvokeeventguid)|[ResourceManagerEventGuid](#resourcemanagereventguid)|
|[ScheduleGroupEventGuid](#schedulegroupeventguid)|[SchedulerEventGuid](#schedulereventguid)|[VirtualProcessorEventGuid](#virtualprocessoreventguid)|

##  <a name="agenteventguid"></a>  AgentEventGuid

Kategoria zdarzenia ETW opisujący wywoływane przez biblioteki agentów w środowisku uruchomieniowym współbieżności: identyfikator GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07}).

```
const __declspec(selectany) GUID AgentEventGuid = {0xb9b5b78c, 0x713, 0x4898, { 0xa2, 0x1a, 0xc6, 0x79, 0x49, 0xdc, 0xed, 0x7 } };
```

##  <a name="choreeventguid"></a>  ChoreEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z infrastrukturą lub zadania.

```
const __declspec(selectany) GUID ChoreEventGuid =
    { 0x7E854EC7, 0xCDC4, 0x405a, { 0xB5, 0xB2, 0xAA, 0xF7, 0xC9, 0xE7, 0xD4, 0x0C } };
```

### <a name="remarks"></a>Uwagi

Ta kategoria zdarzeń nie jest obecnie uruchamiany przez środowisko uruchomieniowe współbieżności.

##  <a name="concrt_providerguid"></a>  ConcRT_ProviderGuid

Dostawca ETW identyfikator GUID dla środowiska uruchomieniowego współbieżności.

```
const __declspec(selectany) GUID ConcRT_ProviderGuid =
    { 0xF7B697A3, 0x4DB5, 0x4d3b, { 0xBE, 0x71, 0xC4, 0xD2, 0x84, 0xE6, 0x59, 0x2F } };
```

##  <a name="concrt_rm_version_1"></a>  CONCRT_RM_VERSION_1

Wskazuje obsługę interfejsu Menedżera zasobów, zdefiniowane w programie Visual Studio 2010.

```
const unsigned int CONCRT_RM_VERSION_1 = 0x00010000;
```

##  <a name="concrteventguid"></a>  ConcRTEventGuid

Kategoria GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które nie zostały dokładniej opisane przez inną kategorię.

```
const __declspec(selectany) GUID ConcRTEventGuid =
    { 0x72B14A7D, 0x704C, 0x423e, { 0x92, 0xF8, 0x7E, 0x6D, 0x64, 0xBC, 0xB9, 0x2A } };
```

### <a name="remarks"></a>Uwagi

Ta kategoria zdarzeń nie jest obecnie uruchamiany przez środowisko uruchomieniowe współbieżności.

##  <a name="cooperative_timeout_infinite"></a>  COOPERATIVE_TIMEOUT_INFINITE

Wartość wskazująca, że oczekiwania nigdy nie powinny wygasać.

```
const unsigned int COOPERATIVE_TIMEOUT_INFINITE = (unsigned int)-1;
```

##  <a name="cooperative_wait_timeout"></a>  COOPERATIVE_WAIT_TIMEOUT

Wartość wskazująca, czy upłynął limit czasu oczekiwania.

```
const size_t COOPERATIVE_WAIT_TIMEOUT = SIZE_MAX;
```

##  <a name="contexteventguid"></a>  ContextEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z kontekstów.

```
const __declspec(selectany) GUID ContextEventGuid =
    { 0x5727A00F, 0x50BE, 0x4519, { 0x82, 0x56, 0xF7, 0x69, 0x98, 0x71, 0xFE, 0xCB } };
```

##  <a name="inherit_thread_priority"></a>  INHERIT_THREAD_PRIORITY

Specjalna wartość klucza zasad `ContextPriority` wskazujący, że priorytet wątku wszystkie konteksty w ramach harmonogramu zadań powinna być taka sama, jak w przypadku wątku, na którym utworzono harmonogram.

```
const unsigned int INHERIT_THREAD_PRIORITY = 0x0000F000;
```

##  <a name="lockeventguid"></a>  LockEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z blokad.

```
const __declspec(selectany) GUID LockEventGuid =
    { 0x79A60DC6, 0x5FC8, 0x4952, { 0xA4, 0x1C, 0x11, 0x63, 0xAE, 0xEC, 0x5E, 0xB8 } };
```

### <a name="remarks"></a>Uwagi

Ta kategoria zdarzeń nie jest obecnie uruchamiany przez środowisko uruchomieniowe współbieżności.

##  <a name="maxexecutionresources"></a>  MaxExecutionResources

Specjalna wartość klucza zasad `MinConcurrency` i `MaxConcurrency`. Wartość domyślna to liczba wątków sprzętu na komputerze, w przypadku braku inne ograniczenia.

```
const unsigned int MaxExecutionResources = 0xFFFFFFFF;
```

##  <a name="pplparallelforeventguid"></a>  PPLParallelForEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z użytkowania `parallel_for` funkcji.

```
const __declspec(selectany) GUID PPLParallelForEventGuid =
    { 0x31c8da6b, 0x6165, 0x4042, { 0x8b, 0x92, 0x94, 0x9e, 0x31, 0x5f, 0x4d, 0x84 } };
```

##  <a name="pplparallelforeacheventguid"></a>  PPLParallelForeachEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z użytkowania `parallel_for_each` funkcji.

```
const __declspec(selectany) GUID PPLParallelForeachEventGuid =
    { 0x5cb7d785, 0x9d66, 0x465d, { 0xba, 0xe1, 0x46, 0x11, 0x6, 0x1b, 0x54, 0x34 } };
```

##  <a name="pplparallelinvokeeventguid"></a>  PPLParallelInvokeEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z użytkowania `parallel_invoke` funkcji.

```
const __declspec(selectany) GUID PPLParallelInvokeEventGuid =
    { 0xd1b5b133, 0xec3d, 0x49f4, { 0x98, 0xa3, 0x46, 0x4d, 0x1a, 0x9e, 0x46, 0x82 } };
```

##  <a name="resourcemanagereventguid"></a>  ResourceManagerEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z usługi resource manager.

```
const __declspec(selectany) GUID ResourceManagerEventGuid =
    { 0x2718D25B, 0x5BF5, 0x4479, { 0x8E, 0x88, 0xBA, 0xBC, 0x64, 0xBD, 0xBF, 0xCA } };
```

### <a name="remarks"></a>Uwagi

Ta kategoria zdarzeń nie jest obecnie uruchamiany przez środowisko uruchomieniowe współbieżności.

##  <a name="schedulegroupeventguid"></a>  ScheduleGroupEventGuid

Kategoria GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z grupy harmonogramu.

```
const __declspec(selectany) GUID ScheduleGroupEventGuid =
    { 0xE8A3BF1F, 0xA86B, 0x4390, { 0x9C, 0x60, 0x53, 0x90, 0xB9, 0x69, 0xD2, 0x2C } };
```

### <a name="remarks"></a>Uwagi

Ta kategoria zdarzeń nie jest obecnie uruchamiany przez środowisko uruchomieniowe współbieżności.

##  <a name="schedulereventguid"></a>  SchedulerEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z harmonogramu działania.

```
const __declspec(selectany) GUID SchedulerEventGuid =
    { 0xE2091F8A, 0x1E0A, 0x4731, { 0x84, 0xA2, 0x0D, 0xD5, 0x7C, 0x8A, 0x52, 0x61 } };
```

##  <a name="virtualprocessoreventguid"></a>  VirtualProcessorEventGuid

Kategorię GUID zawierająca opis zdarzenia ETW wywoływane przez środowisko uruchomieniowe współbieżności, które są bezpośrednio związane z procesorów wirtualnych.

```
const __declspec(selectany) GUID VirtualProcessorEventGuid =
    { 0x2f27805f, 0x1676, 0x4ecc, { 0x96, 0xfa, 0x7e, 0xb0, 0x9d, 0x44, 0x30, 0x2f } };
```

## <a name="see-also"></a>Zobacz także

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
