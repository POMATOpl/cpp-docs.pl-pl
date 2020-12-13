---
description: 'Dowiedz się więcej na temat: Klasa CComApartment'
title: Klasa CComApartment
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: de51d1eb04bfa0f0760ad741e19b237a9e72dc8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152324"
---
# <a name="ccomapartment-class"></a>Klasa CComApartment

Ta klasa zapewnia obsługę zarządzania apartamentem w module programu EXE w puli wątków.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CComApartment
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComApartment:: Apartment](#apartment)|Oznacza adres początkowy wątku.|
|[CComApartment::GetLockCount](#getlockcount)|Zwraca bieżącą liczbę blokad wątku.|
|[CComApartment:: Lock](#lock)|Zwiększa liczbę blokad wątku.|
|[CComApartment:: Unlock](#unlock)|Zmniejsza liczbę blokad wątku.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CComApartment:: m_dwThreadID](#m_dwthreadid)|Zawiera identyfikator wątku.|
|[CComApartment:: m_hThread](#m_hthread)|Zawiera uchwyt wątku.|
|[CComApartment:: m_nLockCnt](#m_nlockcnt)|Zawiera bieżącą liczbę blokad wątku.|

## <a name="remarks"></a>Uwagi

`CComApartment` jest używany przez [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) do zarządzania apartamentem w module programu exe w puli wątków. `CComApartment` zapewnia metody zwiększania i zmniejszania liczby blokad w wątku.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a> CComApartment:: Apartment

Oznacza adres początkowy wątku.

```
DWORD Apartment();
```

### <a name="return-value"></a>Wartość zwracana

Zawsze 0.

### <a name="remarks"></a>Uwagi

Ustawiana automatycznie podczas [CComAutoThreadModule:: init](../../atl/reference/ccomautothreadmodule-class.md#init).

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a> CComApartment::CComApartment

Konstruktor.

```
CComApartment();
```

### <a name="remarks"></a>Uwagi

Inicjuje `CComApartment` składowe danych [m_nLockCnt](#m_nlockcnt) i [m_hThread](#m_hthread).

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a> CComApartment::GetLockCount

Zwraca bieżącą liczbę blokad wątku.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Wartość zwracana

Liczba blokad w wątku.

## <a name="ccomapartmentlock"></a><a name="lock"></a> CComApartment:: Lock

Zwiększa liczbę blokad wątku.

```
LONG Lock();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki lub testowania.

### <a name="remarks"></a>Uwagi

Wywoływane przez [CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Liczba blokad w wątku jest używana do celów statystycznych.

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a> CComApartment:: m_dwThreadID

Zawiera identyfikator wątku.

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a> CComApartment:: m_hThread

Zawiera uchwyt wątku.

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a> CComApartment:: m_nLockCnt

Zawiera bieżącą liczbę blokad wątku.

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a> CComApartment:: Unlock

Zmniejsza liczbę blokad wątku.

```
LONG Unlock();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki lub testowania.

### <a name="remarks"></a>Uwagi

Wywoływane przez [CComAutoThreadModule:: Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Liczba blokad w wątku jest używana do celów statystycznych.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
