---
description: 'Dowiedz się więcej na temat: Klasa CNoWorkerThread'
title: Klasa CNoWorkerThread
ms.date: 11/04/2016
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 5159c04a8390f8933291f697faccedb7353fb48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141417"
---
# <a name="cnoworkerthread-class"></a>Klasa CNoWorkerThread

Użyj tej klasy jako argumentu dla `MonitorClass` parametru szablonu do buforowania klas, jeśli chcesz wyłączyć konserwację dynamicznej pamięci podręcznej.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CNoWorkerThread
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CNoWorkerThread:: AddHandle](#addhandle)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|
|[CNoWorkerThread:: addtimeer](#addtimer)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Addtimeer](../../atl/reference/cworkerthread-class.md#addtimer).|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|
|[CNoWorkerThread::GetThreadId](#getthreadid)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[CNoWorkerThread:: Initialize](#initialize)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize).|
|[CNoWorkerThread::RemoveHandle](#removehandle)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|
|[CNoWorkerThread:: Shutdown](#shutdown)|Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia ten sam interfejs publiczny co [CWorkerThread](../../atl/reference/cworkerthread-class.md). Ten interfejs powinien być dostarczony przez `MonitorClass` parametr szablonu do buforowania klas.

Metody w tej klasie są implementowane, aby nic nie robić. Metody, które zwracają wynik HRESULT zawsze zwracają S_OK, a metody, które zwracają uchwyt lub identyfikator wątku zawsze zwracają 0.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a> CNoWorkerThread:: AddHandle

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca S_OK.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a> CNoWorkerThread:: addtimeer

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Addtimeer](../../atl/reference/cworkerthread-class.md#addtimer).

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca S_OK.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a> CNoWorkerThread::GetThreadHandle

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość NULL.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a> CNoWorkerThread::GetThreadId

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość 0.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a> CNoWorkerThread:: Initialize

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize).

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca S_OK.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a> CNoWorkerThread::RemoveHandle

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca S_OK.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a> CNoWorkerThread:: Shutdown

Odpowiednik niefunkcjonalny elementu [CWorkerThread:: Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca S_OK.

### <a name="remarks"></a>Uwagi

Implementacja udostępniona przez tę klasę nie wykonuje żadnych operacji.
