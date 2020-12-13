---
description: Dowiedz się więcej o strukturze IUMSCompletionList
title: IUMSCompletionList — Struktura
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: b54766e8b1c6f2e7c0afbb5e4e9a8efc0c455b4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334349"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList — Struktura

Reprezentuje listę uzupełniania UMS. Po zablokowaniu wątku UMS, wyznaczoną w harmonogramie kontekst planowania jest wysyłany w celu podjęcia decyzji o tym, co należy zaplanować na źródłowym głównym procesorze wirtualnym, gdy oryginalny wątek jest zablokowany. Gdy oryginalny wątek zostanie odblokowany, system operacyjny kolejkuje go do listy uzupełniania dostępnej za pomocą tego interfejsu. Harmonogram może wysyłać zapytania do listy uzupełniania w wydzielonym kontekście planowania lub innym miejscu, w którym szuka pracy.

## <a name="syntax"></a>Składnia

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IUMSCompletionList:: GetUnblockNotifications —](#getunblocknotifications)|Pobiera łańcuch `IUMSUnblockNotification` interfejsów reprezentujący konteksty wykonywania, których skojarzone serwery proxy wątków zostały odblokowane od czasu ostatniego wywołania tej metody.|

## <a name="remarks"></a>Uwagi

W harmonogramie należy bardzo uważnie informacje o akcjach wykonywanych po użyciu tego interfejsu do usuwania elementów z listy uzupełniania. Elementy powinny być umieszczone na liście kontekstów możliwy do uruchomienia i być ogólnie dostępne tak szybko, jak to możliwe. Jest to w pełni możliwe, że jeden z elementów usuniętych z kolejki uzyskał własność arbitralnej blokady. Harmonogram może nie wprowadzać żadnych dowolnych wywołań funkcji, które mogą blokować między wywołaniem elementu unqueueing a umieszczeniem tych elementów na liście, do której można uzyskać ogólne dostęp z poziomu harmonogramu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IUMSCompletionList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a> IUMSCompletionList:: GetUnblockNotifications —, Metoda

Pobiera łańcuch `IUMSUnblockNotification` interfejsów reprezentujący konteksty wykonywania, których skojarzone serwery proxy wątków zostały odblokowane od czasu ostatniego wywołania tej metody.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Łańcuch `IUMSUnblockNotification` interfejsów.

### <a name="remarks"></a>Uwagi

Zwrócone powiadomienia są nieprawidłowe po przeplanowaniu kontekstów wykonywania.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Struktura IUMSScheduler](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification — Struktura](iumsunblocknotification-structure.md)
