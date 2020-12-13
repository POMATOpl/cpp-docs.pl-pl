---
description: Dowiedz się więcej na temat klasy invalid_multiple_scheduling
title: invalid_multiple_scheduling — Klasa
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: 23d89d93c953a3c01a6e0e698cfa7489effd2986
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334554"
---
# <a name="invalid_multiple_scheduling-class"></a>invalid_multiple_scheduling — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `task_handle` obiekt jest zaplanowany wiele razy przy użyciu `run` metody `task_group` lub `structured_task_group` obiektu bez wywołania wywołującego do albo `wait` `run_and_wait` metody.

## <a name="syntax"></a>Składnia

```cpp
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Przeciążone. Konstruuje `invalid_multiple_scheduling` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_multiple_scheduling"></a><a name="ctor"></a> invalid_multiple_scheduling

Konstruuje `invalid_multiple_scheduling` obiekt.

```cpp
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa task_handle](task-handle-class.md)<br/>
[Klasa task_group](task-group-class.md)<br/>
[wykonane](task-group-class.md)<br/>
[trwa](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[Klasa structured_task_group](structured-task-group-class.md)
