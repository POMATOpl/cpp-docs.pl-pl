---
description: Dowiedz się więcej na temat klasy missing_wait
title: missing_wait — Klasa
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: bfbfdf4c2a52573d08c048bac278386aed1dc5a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202187"
---
# <a name="missing_wait-class"></a>missing_wait — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy istnieją zadania, które w dalszym ciągu zaplanowano do `task_group` `structured_task_group` obiektu lub w momencie wykonania destruktora obiektu. Ten wyjątek nigdy nie zostanie wygenerowany, jeśli destruktor zostanie osiągnięty z powodu odwinięcia stosu w wyniku wyjątku.

## <a name="syntax"></a>Składnia

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[missing_wait](#ctor)|Przeciążone. Konstruuje `missing_wait` obiekt.|

## <a name="remarks"></a>Uwagi

Nieobecny przepływ wyjątku, użytkownik jest odpowiedzialny za wywołanie `wait` albo `run_and_wait` metody lub obiektu `task_group` , `structured_task_group` przed umożliwieniem temu obiektowi. Środowisko uruchomieniowe zgłasza ten wyjątek jako wskazanie, że nie można wywołać `wait` `run_and_wait` metody lub.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`missing_wait`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="missing_wait"></a><a name="ctor"></a> missing_wait

Konstruuje `missing_wait` obiekt.

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa task_group](task-group-class.md)<br/>
[trwa](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[Klasa structured_task_group](structured-task-group-class.md)
