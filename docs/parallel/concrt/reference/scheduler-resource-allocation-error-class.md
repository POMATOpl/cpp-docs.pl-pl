---
description: Dowiedz się więcej na temat klasy scheduler_resource_allocation_error
title: scheduler_resource_allocation_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 50f84cbf76d30a415e2393797baa7d6cfa1e89f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188732"
---
# <a name="scheduler_resource_allocation_error-class"></a>scheduler_resource_allocation_error — Klasa

Ta klasa opisuje wyjątek zgłoszony z powodu niepowodzenia uzyskania zasobu krytycznego w środowisko uruchomieniowe współbieżności.

## <a name="syntax"></a>Składnia

```cpp
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Przeciążone. Konstruuje `scheduler_resource_allocation_error` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_error_code](#get_error_code)|Zwraca kod błędu, który spowodował wyjątek.|

## <a name="remarks"></a>Uwagi

Ten wyjątek jest zazwyczaj generowany w przypadku niepowodzenia wywołania systemu operacyjnego z środowisko uruchomieniowe współbieżności. Kod błędu, który zwykle jest zwracany z wywołania metody Win32, `GetLastError` jest konwertowany na wartość typu `HRESULT` i można go pobrać za pomocą `get_error_code` metody.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="get_error_code"></a><a name="get_error_code"></a> get_error_code

Zwraca kod błędu, który spowodował wyjątek.

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Wartość zwracana

`HRESULT`Wartość błędu, który spowodował wyjątek.

## <a name="scheduler_resource_allocation_error"></a><a name="ctor"></a> scheduler_resource_allocation_error

Konstruuje `scheduler_resource_allocation_error` obiekt.

```cpp
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

*_Hresult*<br/>
`HRESULT`Wartość błędu, który spowodował wyjątek.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
