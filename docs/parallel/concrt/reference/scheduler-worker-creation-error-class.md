---
description: Dowiedz się więcej na temat klasy scheduler_worker_creation_error
title: scheduler_worker_creation_error — Klasa
ms.date: 11/04/2016
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
ms.openlocfilehash: f0fbb0aed19738bb88e4cbfe3a72580627c4fca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188719"
---
# <a name="scheduler_worker_creation_error-class"></a>scheduler_worker_creation_error — Klasa

Ta klasa opisuje wyjątek zgłoszony z powodu błędu tworzenia kontekstu wykonywania procesu roboczego w środowisko uruchomieniowe współbieżności.

## <a name="syntax"></a>Składnia

```cpp
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Przeciążone. Konstruuje `scheduler_worker_creation_error` obiekt.|

## <a name="remarks"></a>Uwagi

Ten wyjątek jest zazwyczaj generowany, gdy wywołanie systemu operacyjnego w celu utworzenia kontekstów wykonywania z poziomu środowisko uruchomieniowe współbieżności zakończy się niepowodzeniem. Konteksty wykonywania to wątki wykonujące zadania w środowisko uruchomieniowe współbieżności. Kod błędu, który zwykle jest zwracany z wywołania metody Win32, `GetLastError` jest konwertowany na wartość typu `HRESULT` i można go pobrać za pomocą metody klasy bazowej `get_error_code` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="scheduler_worker_creation_error"></a><a name="ctor"></a> scheduler_worker_creation_error

Konstruuje `scheduler_worker_creation_error` obiekt.

```cpp
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

*_Hresult*<br/>
`HRESULT`Wartość błędu, który spowodował wyjątek.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
