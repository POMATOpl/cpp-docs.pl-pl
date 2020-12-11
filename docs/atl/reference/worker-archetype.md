---
description: 'Dowiedz się więcej o: proces roboczy Archetype'
title: Archetype procesu roboczego
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 8cb8c2b281bbdc074bb700b77a856f4d26c26cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157571"
---
# <a name="worker-archetype"></a>Archetype procesu roboczego

Klasy, które są zgodne z archetypeem *roboczym* , udostępniają kod do przetwarzania elementów roboczych w kolejce w puli wątków.

**Implementacja**

Aby zaimplementować klasę, która jest zgodna z tym Archetype, Klasa musi udostępniać następujące funkcje:

|Metoda|Opis|
|------------|-----------------|
|[Inicjowanie](#initialize)|Wywołuje się, by zainicjować obiekt Worker przed przekazaniem żądań do [wykonania](#execute).|
|[Wykonaj polecenie](#execute)|Wywołuje się, by przetworzyć element roboczy.|
|[Zakończ](#terminate)|Wywołuje się, by zainicjować obiekt roboczy po przekazaniu wszystkich żądań do [wykonania](#execute).|

|Własne|Opis|
|-------------|-----------------|
|[RequestType](#requesttype)|Element typedef dla typu elementu roboczego, który może być przetwarzany przez klasę Worker.|

Typowa Klasa *procesu roboczego* wygląda następująco:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Istniejące implementacje**

Te klasy są zgodne z tym Archetype:

|Klasa|Opis|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Odbiera żądania z puli wątków i przekazuje je do obiektu procesu roboczego, który jest tworzony i niszczony dla każdego żądania.|

**Zastosowanie**

Te parametry szablonu oczekują, aby Klasa była zgodna z tą Archetype:

|Nazwa parametru|Używane przez|
|--------------------|-------------|
|*Odpowiedzialn*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Odpowiedzialn*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="workerarchetypeexecute"></a><a name="execute"></a> WorkerArchetype:: Execute

Wywołuje się, by przetworzyć element roboczy.

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parametry

*żądając*<br/>
Element roboczy, który ma zostać przetworzony. Element roboczy jest tego samego typu co `RequestType` .

*pvWorkerParam*<br/>
Niestandardowy parametr zrozumiały dla klasy Worker. Przeszedł również do `WorkerArchetype::Initialize` i `Terminate` .

*pOverlapped*<br/>
Wskaźnik do [NAkładającego](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) się struktury użytego do utworzenia kolejki, w której elementy robocze zostały umieszczone w kolejce.

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a> WorkerArchetype:: Initialize

Wywołuje się, by zainicjować obiekt Worker przed przekazaniem żądań do `WorkerArchetype::Execute` .

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametry

*pvParam*<br/>
Niestandardowy parametr zrozumiały dla klasy Worker. Przeszedł również do `WorkerArchetype::Terminate` i `WorkerArchetype::Execute` .

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a> WorkerArchetype:: RequestType

Element typedef dla typu elementu roboczego, który może być przetwarzany przez klasę Worker.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Uwagi

Ten typ musi być używany jako pierwszy parametr `WorkerArchetype::Execute` i musi być w stanie rzutować do i z ULONG_PTR.

## <a name="workerarchetypeterminate"></a><a name="terminate"></a> WorkerArchetype:: Przerwij

Wywołuje się, by zainicjować obiekt roboczy po przekazaniu wszystkich żądań do `WorkerArchetype::Execute` ).

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parametry

*pvParam*<br/>
Niestandardowy parametr zrozumiały dla klasy Worker. Przeszedł również do `WorkerArchetype::Initialize` i `WorkerArchetype::Execute` .

## <a name="see-also"></a>Zobacz też

[Pojęcia](../../atl/active-template-library-atl-concepts.md)<br/>
[Składniki ATL COM pulpitu](../../atl/atl-com-desktop-components.md)
