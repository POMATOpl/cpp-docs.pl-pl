---
title: Obsługa zdarzeń w natywnym kodzie C++
description: Dowiedz się, jak używać rozszerzeń języka Microsoft C++ do natywnej obsługi zdarzeń C++.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: 5ad9128b7ff596674c3b08687b722c81b7a10aa8
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483181"
---
# <a name="event-handling-in-native-c"></a>Obsługa zdarzeń w natywnym kodzie C++

W natywnej obsłudze zdarzeń C++ można skonfigurować źródło zdarzeń i odbiorcę zdarzeń przy użyciu odpowiednio atrybutów [event_source](../windows/attributes/event-source.md) i [event_receiver](../windows/attributes/event-receiver.md) `type` = `native` . Te atrybuty umożliwiają stosowanie klas, w których są stosowane, aby uruchamiać zdarzenia i obsługiwać zdarzenia w natywnym kontekście, innym niż COM.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="declaring-events"></a>Deklarowanie zdarzeń

W klasie źródła zdarzeń, użyj [`__event`](../cpp/event.md) słowa kluczowego w deklaracji metody, aby zadeklarować metodę jako zdarzenie. Pamiętaj, aby zadeklarować metodę, ale nie należy jej definiować. Jeśli to zrobisz, generuje błąd kompilatora, ponieważ kompilator definiuje metodę niejawnie, gdy jest wykonywana w zdarzeniu. Zdarzenia natywne mogą być metodami z zero lub więcej parametrami. Zwracany typ może być **`void`** lub dowolnego typu całkowitego.

## <a name="defining-event-handlers"></a>Definiowanie programów obsługi zdarzeń

W klasie odbiorcy zdarzeń należy zdefiniować programy obsługi zdarzeń. Programy obsługi zdarzeń to metody z sygnaturami (typy zwracane, konwencje wywoływania i argumenty), które pasują do zdarzenia, które będą obsługiwane.

## <a name="hooking-event-handlers-to-events"></a>Podłączanie programów obsługi zdarzeń do zdarzeń

Również w klasie odbiorcy zdarzeń, funkcja wewnętrzna służy [`__hook`](../cpp/hook.md) do kojarzenia zdarzeń z obsługą zdarzeń oraz [`__unhook`](../cpp/unhook.md) do usuwania skojarzeń zdarzeń z programów obsługi zdarzeń. Można podłączyć kilka zdarzeń do programu obsługi zdarzeń lub kilka programów obsługi zdarzeń do zdarzenia.

## <a name="firing-events"></a>Wyzwalanie zdarzeń

Aby wywołać zdarzenie, wywołaj metodę zadeklarowaną jako zdarzenie w klasie Źródło zdarzenia. Jeśli programy obsługi zostały podłączone do zdarzenia, zostaną wywołane programy obsługi.

### <a name="native-c-event-code"></a>Natywny kod zdarzenia C++

Poniższy przykład pokazuje, jak uruchomić zdarzenie w natywnym języku C++. Aby skompilować i uruchomić przykład, zobacz komentarze w kodzie. Aby skompilować kod w środowisku IDE programu Visual Studio, sprawdź, czy **`/permissive-`** opcja jest wyłączona.

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```cpp
// evh_native.cpp
// compile by using: cl /EHsc /W3 evh_native.cpp
#include <stdio.h>

[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};

[event_receiver(native)]
class CReceiver {
public:
   void MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
   }

   void MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
   }

   void hookEvent(CSource* pSource) {
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void unhookEvent(CSource* pSource) {
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   CSource source;
   CReceiver receiver;

   receiver.hookEvent(&source);
   __raise source.MyEvent(123);
   receiver.unhookEvent(&source);
}
```

### <a name="output"></a>Dane wyjściowe

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>Zobacz także

[Obsługa zdarzeń](../cpp/event-handling.md)
