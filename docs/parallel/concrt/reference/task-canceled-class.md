---
description: Dowiedz się więcej na temat klasy task_canceled
title: task_canceled — Klasa
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: 223a1168464e312c272f770247b3574311ff97ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188407"
---
# <a name="task_canceled-class"></a>task_canceled — Klasa

Ta klasa opisuje wyjątek zgłoszony przez warstwę zadań PPL w celu wymuszenia anulowania bieżącego zadania. Jest on również generowany przez `get()` metodę w [zadaniu](/visualstudio/extensibility/debugger/task-class-internal-members)dla anulowanego zadania.

## <a name="syntax"></a>Składnia

```cpp
class task_canceled : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[task_canceled](#ctor)|Przeciążone. Konstruuje `task_canceled` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`task_canceled`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="task_canceled"></a><a name="ctor"></a> task_canceled

Konstruuje `task_canceled` obiekt.

```cpp
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
