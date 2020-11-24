---
title: Obsługa zdarzeń w modelu COM
description: Dowiedz się, jak używać rozszerzeń języka Microsoft C++ do obsługi zdarzeń COM.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.openlocfilehash: 0c664f052fe211c88ad097c9d2617ec47f180eff
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483116"
---
# <a name="event-handling-in-com"></a>Obsługa zdarzeń w modelu COM

W obsłudze zdarzeń COM należy skonfigurować źródło zdarzeń i odbiorcę zdarzeń przy użyciu [`event_source`](../windows/attributes/event-source.md) [`event_receiver`](../windows/attributes/event-receiver.md) odpowiednio atrybutów i `type` = `com` . Te atrybuty wprowadzają odpowiedni kod dla niestandardowych, wysyłanych i podwójnych interfejsów. Wprowadzony kod zezwala klasie z atrybutami na Wyzwalanie zdarzeń i obsługę zdarzeń za pomocą punktów połączenia COM.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="declaring-events"></a>Deklarowanie zdarzeń

W klasie źródła zdarzeń, użyj [`__event`](../cpp/event.md) słowa kluczowego w deklaracji interfejsu, aby zadeklarować metody tego interfejsu jako zdarzenia. Zdarzenia tego interfejsu są uruchamiane podczas wywoływania ich jako metod interfejsu. Metody interfejsów zdarzeń mogą mieć zero lub więcej parametrów (które powinny znajdować się *w* parametrach). Zwracany typ może być typu void lub dowolnego całkowitego.

## <a name="defining-event-handlers"></a>Definiowanie programów obsługi zdarzeń

Programy obsługi zdarzeń definiuje się w klasie odbiorcy zdarzeń. Programy obsługi zdarzeń to metody z sygnaturami (typy zwracane, konwencje wywoływania i argumenty), które pasują do zdarzenia, które będą obsługiwane. W przypadku zdarzeń COM konwencje wywoływania nie muszą być zgodne. Aby uzyskać więcej informacji, zobacz [zdarzenia com zależne od układu](#vcconeventhandlingincomanchorlayoutdependentcomevents) poniżej.

## <a name="hooking-event-handlers-to-events"></a>Podłączanie programów obsługi zdarzeń do zdarzeń

Również w klasie odbiorcy zdarzeń, funkcja wewnętrzna służy [`__hook`](../cpp/hook.md) do kojarzenia zdarzeń z obsługą zdarzeń oraz [`__unhook`](../cpp/unhook.md) do usuwania skojarzeń zdarzeń z programów obsługi zdarzeń. Można podłączyć kilka zdarzeń do programu obsługi zdarzeń lub kilka programów obsługi zdarzeń do zdarzenia.

> [!NOTE]
> Zwykle istnieją dwie techniki udostępniające odbiorcy zdarzenia COM definicje interfejsu źródła zdarzeń. Pierwszą techniką, jak pokazano poniżej, jest udostępnienie wspólnego pliku nagłówkowego. Drugim jest użycie [#import](../preprocessor/hash-import-directive-cpp.md) z `embedded_idl` kwalifikatorem importu, tak aby biblioteka typów źródła zdarzeń była zapisywana w pliku TLH z zachowaniem kodu generowanego przez atrybut.

## <a name="firing-events"></a>Wyzwalanie zdarzeń

Aby wyzwolić zdarzenie, należy wywołać metodę w interfejsie zadeklarowanym ze **`__event`** słowem kluczowym w klasie źródła zdarzenia. Jeśli programy obsługi zostały podłączone do zdarzenia, zostaną wywołane programy obsługi.

### <a name="com-event-code"></a>Kod zdarzenia COM

Poniższy przykład pokazuje jak wywołać zdarzenie w klasie COM. Aby skompilować i uruchomić przykład, zobacz komentarze w kodzie.

```cpp
// evh_server.h
#pragma once

[ dual, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IEvents {
   [id(1)] HRESULT MyEvent([in] int value);
};

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT FireEvent();
};

class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;
```

A następnie serwera:

```cpp
// evh_server.cpp
// compile with: /LD
// post-build command: Regsvr32.exe /s evh_server.dll
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include "evh_server.h"

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      __raise MyEvent(123);
      return S_OK;
   }
};
```

A następnie klienta:

```cpp
// evh_client.cpp
// compile with: /link /OPT:NOREF
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <stdio.h>
#include "evh_server.h"

[ module(name="EventReceiver") ];

[ event_receiver(com) ]
class CReceiver {
public:
   HRESULT MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
      return S_OK;
   }

   HRESULT MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
      return S_OK;
   }

   void HookEvent(IEventSource* pSource) {
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void UnhookEvent(IEventSource* pSource) {
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   // Create COM object
   CoInitialize(NULL);
   {
      IEventSource* pSource = 0;
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);
      if (FAILED(hr)) {
         return -1;
      }

      // Create receiver and fire event
      CReceiver receiver;
      receiver.HookEvent(pSource);
      pSource->FireEvent();
      receiver.UnhookEvent(pSource);
   }
   CoUninitialize();
   return 0;
}
```

### <a name="output"></a>Dane wyjściowe

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

## <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Zdarzenia COM zależne od układu

Zależność układu jest tylko problemem programowania COM. W natywnej i zarządzanej obsłudze zdarzeń, podpisy (typ zwracany, Konwencja wywoływania i argumenty) programów obsługi muszą być zgodne ze swoimi zdarzeniami, ale nazwy programu obsługi nie muszą odpowiadać ich zdarzeniom.

Jednak w obsłudze zdarzeń COM, podczas ustawiania *`layout_dependent`* parametru `event_receiver` do **`true`** , jest wymuszane dopasowanie nazwy i podpisu. Nazwy i podpisy programów obsługi w odbiorniku zdarzeń oraz zdarzenia podłączane muszą dokładnie pasować.

Gdy *`layout_dependent`* jest ustawiona na **`false`** , Konwencja wywoływania i Klasa magazynu (wirtualne, statyczne i tak dalej) mogą być mieszane i dopasowywane między metodą zdarzenia wyzwalania a metodami podłączania (jego delegatów). Jest nieco bardziej wydajny *`layout_dependent`* = **`true`** .

Załóżmy, że `IEventSource` jest zdefiniowany dla następujących metod:

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

Przyjęto założenie, że źródło zdarzenia ma następującą postać:

```cpp
[coclass, event_source(com)]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      MyEvent1(123);
      MyEvent2(123);
      return S_OK;
   }
};
```

Następnie, w przypadku odbiornika, każdy program obsługi podłączony do metody w `IEventSource` musi odpowiadać jej nazwie i podpisie, w następujący sposób:

```cpp
[coclass, event_receiver(com, true)]
class CReceiver {
public:
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1
      ...
   }
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2
      ...
   }
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)
      ...
   }
   void HookEvent(IEventSource* pSource) {
      __hook(IFace, pSource);  // Hooks up all name-matched events
                               // under layout_dependent = true
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid
   }
};
```

## <a name="see-also"></a>Zobacz także

[Obsługa zdarzeń](../cpp/event-handling.md)
