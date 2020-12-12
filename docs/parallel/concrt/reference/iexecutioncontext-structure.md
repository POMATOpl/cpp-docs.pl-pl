---
description: Dowiedz się więcej o strukturze IExecutionContext
title: IExecutionContext — Struktura
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 90802229e878546383f683bc99ffedc9cb5411af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122190"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext — Struktura

Interfejs do kontekstu wykonywania, który może być uruchamiany w danym procesorze wirtualnym i być przełączany w ramach współdziałania z podsiecią.

## <a name="syntax"></a>Składnia

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IExecutionContext::D ispatch](#dispatch)|Metoda wywoływana, gdy serwer proxy wątku uruchamia wykonywanie określonego kontekstu wykonania. Powinna to być główna procedura procesu roboczego dla harmonogramu.|
|[IExecutionContext:: GetId —](#getid)|Zwraca unikatowy identyfikator kontekstu wykonania.|
|[IExecutionContext:: GetProxy](#getproxy)|Zwraca interfejs do serwera proxy wątku, który wykonuje ten kontekst.|
|[IExecutionContext:: getschedulerer](#getscheduler)|Zwraca interfejs do harmonogramu, do którego należy ten kontekst wykonania.|
|[IExecutionContext:: SetProxy](#setproxy)|Kojarzy serwer proxy wątku z tym kontekstem wykonania. Skojarzony serwer proxy wątku wywołuje tę metodę bezpośrednio przed rozpoczęciem wykonywania `Dispatch` metody kontekstu.|

## <a name="remarks"></a>Uwagi

W przypadku wdrażania niestandardowego harmonogramu, który ma interfejsy z Menedżer zasobów środowisko uruchomieniowe współbieżności, należy zaimplementować `IExecutionContext` interfejs. Wątki utworzone przez Menedżer zasobów wykonują pracę w imieniu harmonogramu, wykonując `IExecutionContext::Dispatch` metodę.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IExecutionContext`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a> IExecutionContext::D ispatch — Metoda

Metoda wywoływana, gdy serwer proxy wątku uruchamia wykonywanie określonego kontekstu wykonania. Powinna to być główna procedura procesu roboczego dla harmonogramu.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parametry

*pDispatchState*<br/>
Wskaźnik do stanu, w którym jest wysyłany ten kontekst wykonania. Aby uzyskać więcej informacji o stanie wysyłania, zobacz [DispatchState](dispatchstate-structure.md).

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a> IExecutionContext:: GetId —, Metoda

Zwraca unikatowy identyfikator kontekstu wykonania.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Unikatowy identyfikator liczby całkowitej.

### <a name="remarks"></a>Uwagi

Należy użyć metody `GetExecutionContextId` , aby uzyskać unikatowy identyfikator obiektu, który implementuje `IExecutionContext` interfejs, przed użyciem interfejsu jako parametru do metod dostarczonych przez Menedżer zasobów. Po wywołaniu funkcji należy zwrócić ten sam identyfikator `GetId` .

Identyfikator uzyskany z innego źródła może spowodować niezdefiniowane zachowanie.

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a> IExecutionContext:: GetProxy — Metoda

Zwraca interfejs do serwera proxy wątku, który wykonuje ten kontekst.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Wartość zwracana

`IThreadProxy`Interfejs. Jeśli serwer proxy wątku nie został zainicjowany z wywołaniem `SetProxy` , funkcja musi zwrócić `NULL` .

### <a name="remarks"></a>Uwagi

Menedżer zasobów wywoła `SetProxy` metodę w kontekście wykonywania, przy użyciu `IThreadProxy` interfejsu jako parametru, przed wprowadzeniem `Dispatch` metody w kontekście. Oczekiwany jest zapisanie tego argumentu i zwrócenie go na wywołania `GetProxy()` .

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a> IExecutionContext:: GetScheduler — Metoda

Zwraca interfejs do harmonogramu, do którego należy ten kontekst wykonania.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Wartość zwracana

`IScheduler`Interfejs.

### <a name="remarks"></a>Uwagi

Musisz zainicjować kontekst wykonywania z prawidłowym `IScheduler` interfejsem przed użyciem go jako parametru do metod dostarczonych przez Menedżer zasobów.

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a> IExecutionContext:: SetProxy — Metoda

Kojarzy serwer proxy wątku z tym kontekstem wykonania. Skojarzony serwer proxy wątku wywołuje tę metodę bezpośrednio przed rozpoczęciem wykonywania `Dispatch` metody kontekstu.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parametry

*pThreadProxy*<br/>
Interfejs do serwera proxy wątku, który ma wprowadzić `Dispatch` metodę w tym kontekście wykonania.

### <a name="remarks"></a>Uwagi

Należy zapisać parametr `pThreadProxy` i zwrócić go do wywołania `GetProxy` metody. Menedżer zasobów gwarantuje, że serwer proxy wątku skojarzony z kontekstem wykonywania nie ulegnie zmianie, gdy serwer proxy wątku wykonuje `Dispatch` metodę.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Struktura IScheduler](ischeduler-structure.md)<br/>
[IThreadProxy — Struktura](ithreadproxy-structure.md)
