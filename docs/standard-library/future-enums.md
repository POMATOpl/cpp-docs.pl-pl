---
description: 'Dowiedz się więcej o: &lt; przyszłych &gt; wyliczeń'
title: '&lt;przyszłe &gt; wyliczenia'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 473533d5d22ac5708af7a86cc58a57ac033545af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232138"
---
# <a name="ltfuturegt-enums"></a>&lt;przyszłe &gt; wyliczenia

[future_errc](#future_errc)\
[future_status](#future_status)\
[paska](#launch)

## <a name="future_errc-enumeration"></a><a name="future_errc"></a> future_errc, Wyliczenie

Dostarcza symboliczne nazwy dla wszystkich błędów zgłaszanych przez klasę [future_error](../standard-library/future-error-class.md) .

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status-enumeration"></a><a name="future_status"></a> future_status, Wyliczenie

Dostarcza symboliczne nazwy z przyczyn, które może zwracać funkcja oczekiwania czasowego.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch-enumeration"></a><a name="launch"></a> Uruchom Wyliczenie

Reprezentuje typ maski bitowej, który opisuje możliwe tryby [asynchronicznej](../standard-library/future-functions.md#async)funkcji szablonu.

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>Zobacz też

[\<future>](../standard-library/future.md)
