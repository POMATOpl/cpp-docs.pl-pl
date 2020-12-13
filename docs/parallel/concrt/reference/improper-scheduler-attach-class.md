---
description: Dowiedz się więcej na temat klasy improper_scheduler_attach
title: improper_scheduler_attach — Klasa
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 755cd72d20eb88dbd1ff7c58586f0aaf3b964a6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334629"
---
# <a name="improper_scheduler_attach-class"></a>improper_scheduler_attach — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `Attach` Metoda jest wywoływana w `Scheduler` obiekcie, który jest już dołączony do bieżącego kontekstu.

## <a name="syntax"></a>Składnia

```cpp
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|Przeciążone. Konstruuje `improper_scheduler_attach` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="improper_scheduler_attach"></a><a name="ctor"></a> improper_scheduler_attach

Konstruuje `improper_scheduler_attach` obiekt.

```cpp
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Scheduler — Klasa](scheduler-class.md)
