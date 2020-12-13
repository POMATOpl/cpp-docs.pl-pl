---
description: Dowiedz się więcej na temat klasy invalid_scheduler_policy_value
title: invalid_scheduler_policy_value — Klasa
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: c91295646b0bc85ea4ed5ee8f376c1ed029e4f0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334495"
---
# <a name="invalid_scheduler_policy_value-class"></a>invalid_scheduler_policy_value — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy klucz zasad `SchedulerPolicy` obiektu jest ustawiony na nieprawidłową wartość dla tego klucza.

## <a name="syntax"></a>Składnia

```cpp
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_scheduler_policy_value] (nieprawidłowy-Scheduler-Policy-Thread-Specification-Class. MD # ctor|Przeciążone. Konstruuje `invalid_scheduler_policy_value` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_scheduler_policy_value"></a><a name="ctor"></a> invalid_scheduler_policy_value

Konstruuje `invalid_scheduler_policy_value` obiekt.

```cpp
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa SchedulerPolicy](schedulerpolicy-class.md)
