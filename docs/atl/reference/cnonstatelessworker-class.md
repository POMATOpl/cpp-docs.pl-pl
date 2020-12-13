---
description: 'Dowiedz się więcej na temat: Klasa CNonStatelessWorker'
title: Klasa CNonStatelessWorker
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 68457c9594bfaf4d8dd53acd80d7997355c3a3f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141430"
---
# <a name="cnonstatelessworker-class"></a>Klasa CNonStatelessWorker

Odbiera żądania z puli wątków i przekazuje je do obiektu procesu roboczego, który jest tworzony i niszczony dla każdego żądania.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Parametry

*Odpowiedzialn*<br/>
Klasa wątku roboczego zgodna z [Archetype procesu roboczego](../../atl/reference/worker-archetype.md) , odpowiednia do obsługi żądań umieszczonych w kolejce w [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CNonStatelessWorker:: RequestType](#requesttype)|Implementacja elementu [WorkerArchetype:: RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CNonStatelessWorker:: Execute](#execute)|Implementacja elementu [WorkerArchetype:: Execute](worker-archetype.md#execute).|
|[CNonStatelessWorker:: Initialize](#initialize)|Implementacja elementu [WorkerArchetype:: Initialize](worker-archetype.md#initialize).|
|[CNonStatelessWorker:: Przerwij](#terminate)|Implementacja elementu [WorkerArchetype:: terminate](worker-archetype.md#terminate).|

## <a name="remarks"></a>Uwagi

Ta klasa jest prostym wątkiem roboczym do użycia z [CThreadPool](../../atl/reference/cthreadpool-class.md). Ta klasa nie zapewnia własnych funkcji obsługi żądań. Zamiast tego tworzy wystąpienie *procesu roboczego* na żądanie i deleguje implementację jego metod do tego wystąpienia.

Zaletą tej klasy jest to, że zapewnia wygodny sposób zmiany modelu stanu dla istniejących klas wątków roboczych. `CThreadPool` utworzy pojedynczy proces roboczy dla okresu istnienia wątku, więc jeśli Klasa procesu roboczego utrzymuje stan, będzie przechowywać ją na wielu żądaniach. Po prostu Zawijaj tę klasę w `CNonStatelessWorker` szablonie przed użyciem jej w programie `CThreadPool` , okres istnienia procesu roboczego i jego stan są ograniczone do pojedynczego żądania.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a> CNonStatelessWorker:: Execute

Implementacja elementu [WorkerArchetype:: Execute](worker-archetype.md#execute).

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Uwagi

Ta metoda tworzy wystąpienie klasy *Worker* na stosie [i wywołuje wywołania](worker-archetype.md#initialize) w tym obiekcie. Jeśli inicjalizacja zakończyła się pomyślnie, ta metoda wywoła również polecenie [Execute](worker-archetype.md#execute) i [Zakończ](worker-archetype.md#terminate) dla tego samego obiektu.

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a> CNonStatelessWorker:: Initialize

Implementacja elementu [WorkerArchetype:: Initialize](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Ta klasa nie wykonuje żadnych inicjalizacji w programie `Initialize` .

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a> CNonStatelessWorker:: RequestType

Implementacja elementu [WorkerArchetype:: RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Uwagi

Ta klasa obsługuje ten sam typ elementu roboczego, co Klasa użyta dla parametru szablonu *procesu roboczego* . Aby uzyskać szczegółowe informacje, zobacz [CNonStatelessWorker Overview (omówienie](../../atl/reference/cnonstatelessworker-class.md) ).

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a> CNonStatelessWorker:: Przerwij

Implementacja elementu [WorkerArchetype:: terminate](worker-archetype.md#terminate).

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Uwagi

Ta klasa nie wykonuje żadnych czynności czyszczących w programie `Terminate` .

## <a name="see-also"></a>Zobacz też

[Klasa CThreadPool](../../atl/reference/cthreadpool-class.md)<br/>
[Archetype procesu roboczego](../../atl/reference/worker-archetype.md)<br/>
[Klasy](../../atl/reference/atl-classes.md)
