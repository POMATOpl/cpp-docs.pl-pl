---
description: Dowiedz się więcej na temat klasy invalid_scheduler_policy_thread_specification
title: invalid_scheduler_policy_thread_specification — Klasa
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: 97a3910fc83e741c54ece51ed8e20686bbd6c66b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334504"
---
# <a name="invalid_scheduler_policy_thread_specification-class"></a>invalid_scheduler_policy_thread_specification — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy podejmowana jest próba ustawienia limitów współbieżności obiektu w `SchedulerPolicy` taki sposób, że wartość `MinConcurrency` klucza jest mniejsza niż wartość `MaxConcurrency` klucza.

## <a name="syntax"></a>Składnia

```cpp
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification] (Nieprawidłowa wartość-Scheduler-Policy-value-class. MD # ctor|Przeciążone. Konstruuje `invalid_scheduler_policy_value` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_scheduler_policy_thread_specification"></a><a name="ctor"></a> invalid_scheduler_policy_thread_specification

Konstruuje `invalid_scheduler_policy_value` obiekt.

```cpp
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa SchedulerPolicy](schedulerpolicy-class.md)
