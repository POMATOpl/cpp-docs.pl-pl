---
description: Dowiedz się więcej na temat klasy invalid_scheduler_policy_key
title: invalid_scheduler_policy_key — Klasa
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: d352246cf0fe94f0ba5ee567f353680c89efcddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334521"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy nieprawidłowy lub nieznany klucz jest przesyłany do `SchedulerPolicy` konstruktora obiektów lub `SetPolicyValue` Metoda `SchedulerPolicy` obiektu jest przenoszona jako klucz, który należy zmienić przy użyciu innych metod, takich jak `SetConcurrencyLimits` Metoda.

## <a name="syntax"></a>Składnia

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Przeciążone. Konstruuje `invalid_scheduler_policy_key` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_scheduler_policy_key"></a><a name="ctor"></a> invalid_scheduler_policy_key

Konstruuje `invalid_scheduler_policy_key` obiekt.

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa SchedulerPolicy](schedulerpolicy-class.md)
