---
description: Dowiedz się więcej na temat klasy default_scheduler_exists
title: default_scheduler_exists — Klasa
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 6921f7bd820271cf590707c2e56cefa9f576cefe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284853"
---
# <a name="default_scheduler_exists-class"></a>default_scheduler_exists — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `Scheduler::SetDefaultSchedulerPolicy` Metoda jest wywoływana, gdy domyślny harmonogram już istnieje w ramach procesu.

## <a name="syntax"></a>Składnia

```cpp
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|Przeciążone. Konstruuje `default_scheduler_exists` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="default_scheduler_exists"></a><a name="ctor"></a> default_scheduler_exists

Konstruuje `default_scheduler_exists` obiekt.

```cpp
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
