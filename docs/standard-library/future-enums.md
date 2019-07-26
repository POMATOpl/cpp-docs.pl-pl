---
title: '&lt;przyszłe&gt; wyliczenia'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: a5bcebd80b296a0b8416580aa03acc59ce3750cd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448226"
---
# <a name="ltfuturegt-enums"></a>&lt;przyszłe&gt; wyliczenia

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[launch](#launch)|

## <a name="future_errc"></a>future_errc, Wyliczenie

Dostarcza symboliczne nazwy dla wszystkich błędów zgłaszanych przez klasę [future_error](../standard-library/future-error-class.md) .

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status"></a>future_status, Wyliczenie

Dostarcza symboliczne nazwy z przyczyn, które może zwracać funkcja oczekiwania czasowego.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch"></a>Uruchom Wyliczenie

Reprezentuje typ maski bitowej, który opisuje możliwe tryby asynchronicznej funkcji szablonu [](../standard-library/future-functions.md#async).

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>Zobacz także

[\<future>](../standard-library/future.md)
