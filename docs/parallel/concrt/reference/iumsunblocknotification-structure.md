---
description: Dowiedz się więcej o strukturze IUMSUnblockNotification
title: IUMSUnblockNotification — Struktura
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: bec40ee1e7326ad37e205c3035f965cb3f0ec8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334309"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification — Struktura

Reprezentuje powiadomienie z Menedżer zasobów, że serwer proxy wątku, który został zablokowany i wyzwolony powrót do wyznaczonego kontekstu planowania harmonogramu został odblokowany i jest gotowy do zaplanowania. Ten interfejs jest nieprawidłowy, gdy kontekst wykonywania skojarzony z serwerem proxy wątku został zwrócony z `GetContext` metody, został ponownie zaplanowany.

## <a name="syntax"></a>Składnia

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IUMSUnblockNotification:: GetContext](#getcontext)|Zwraca `IExecutionContext` interfejs kontekstu wykonywania skojarzony z serwerem proxy wątku, który został odblokowany. Gdy ta metoda zostanie zwrócona, a podstawowy kontekst wykonywania został ponownie zaplanowany za pośrednictwem wywołania `IThreadProxy::SwitchTo` metody, ten interfejs nie jest już prawidłowy.|
|[IUMSUnblockNotification:: GetNextUnblockNotification —](#getnextunblocknotification)|Zwraca następny `IUMSUnblockNotification` interfejs w łańcuchu zwróconym przez metodę `IUMSCompletionList::GetUnblockNotifications` .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IUMSUnblockNotification`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a> IUMSUnblockNotification:: GetContext — Metoda

Zwraca `IExecutionContext` interfejs kontekstu wykonywania skojarzony z serwerem proxy wątku, który został odblokowany. Gdy ta metoda zostanie zwrócona, a podstawowy kontekst wykonywania został ponownie zaplanowany za pośrednictwem wywołania `IThreadProxy::SwitchTo` metody, ten interfejs nie jest już prawidłowy.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Wartość zwracana

`IExecutionContext`Interfejs dla kontekstu wykonywania do serwera proxy wątku, który został odblokowany.

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a> IUMSUnblockNotification:: GetNextUnblockNotification —, Metoda

Zwraca następny `IUMSUnblockNotification` interfejs w łańcuchu zwróconym przez metodę `IUMSCompletionList::GetUnblockNotifications` .

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Następny `IUMSUnblockNotification` interfejs w łańcuchu zwróconym przez metodę `IUMSCompletionList::GetUnblockNotifications` .

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Struktura IUMSScheduler](iumsscheduler-structure.md)<br/>
[IUMSCompletionList — Struktura](iumscompletionlist-structure.md)
