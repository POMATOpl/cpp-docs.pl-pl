---
title: __unhook
description: Dowiedz się, jak używać słowa kluczowego rozszerzenia języka Microsoft C++ `__unhook` do obsługi zdarzeń natywnych.
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.openlocfilehash: 74f8b814ea23c5513b7b73bf90ef59984742a266
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483324"
---
# <a name="__unhook-keyword"></a>`__unhook` kodu

Usuwa metodę procedury obsługi ze zdarzenia.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);

long  __unhook(
   interface,
   source
);

long  __unhook(
   source
);
```

### <a name="parameters"></a>Parametry

*`&SourceClass::EventMethod`*\
Wskaźnik do metody zdarzenia, z której zostanie odłożona metoda obsługi zdarzeń:

- Natywne zdarzenia języka C++: *`SourceClass`* to Klasa źródła zdarzeń, która *`EventMethod`* jest zdarzeniem.

- Zdarzenia COM: *`SourceClass`* jest interfejsem źródła zdarzeń i *`EventMethod`* jest jedną z jej metod.

- Zdarzenia zarządzane: *`SourceClass`* to Klasa źródła zdarzeń, która *`EventMethod`* jest zdarzeniem.

*`interface`*\
Nazwa interfejsu, która jest odłączana od *odbiornika*, tylko dla odbiorników zdarzeń com, w których parametr *layout_dependent* [`event_receiver`](../windows/attributes/event-receiver.md) atrybutu ma wartość **`true`** .

*`source`*\
Wskaźnik do wystąpienia źródła zdarzeń. W zależności od kodu `type` określonego w `event_receiver` , *Źródło* może być jednym z następujących typów:

- Natywny wskaźnik obiektu źródła zdarzenia.

- `IUnknown`Wskaźnik oparty na (źródle com).

- Wskaźnik obiektu zarządzanego (dla zdarzeń zarządzanych).

*`&ReceiverClass::HandlerMethod`* Wskaźnik do metody obsługi zdarzeń, który ma zostać odpinany ze zdarzenia. Procedura obsługi jest określana jako metoda klasy lub odwołania do tego samego; Jeśli nie określisz nazwy klasy, przyjmuje się, że **`__unhook`** Klasa jest klasą, w której jest wywoływana.

- Natywne zdarzenia języka C++: *`ReceiverClass`* to Klasa odbiorcy zdarzeń i `HandlerMethod` jest programem obsługi.

- Zdarzenia COM: *`ReceiverClass`* to interfejs odbiorcy zdarzeń i *`HandlerMethod`* jest jednym z jego obsługi.

- Zdarzenia zarządzane: *`ReceiverClass`* to Klasa odbiorcy zdarzeń i *`HandlerMethod`* jest programem obsługi.

*`receiver`* obowiązkowe Wskaźnik do wystąpienia klasy odbiorcy zdarzeń. Jeśli odbiornik nie zostanie określony, wartością domyślną jest Klasa odbiornika lub struktura, w której **`__unhook`** jest wywoływana.

## <a name="usage"></a>Użycie

Można używać w dowolnym zakresie funkcji, w tym `main` , poza klasą odbiorcy zdarzeń.

## <a name="remarks"></a>Uwagi

Użyj funkcji wewnętrznej **`__unhook`** w odbiorniku zdarzenia, aby usunąć skojarzenie lub "odpina" metodę obsługi z metody zdarzenia.

Istnieją trzy formy **`__unhook`** . W większości przypadków można użyć pierwszego (czterech argumentów) formularza. Można użyć drugiego (dwuargumentowego) formularza **`__unhook`** tylko dla odbiorcy zdarzeń com; odpina cały interfejs zdarzenia. Możesz użyć trzeciego (jednego argumentu) formularza, aby odpiąć wszystkie delegatów z określonego źródła.

Wartość zwrotna niezerowa wskazuje, że wystąpił błąd (zdarzenia zarządzane spowodują zgłoszenie wyjątku).

Jeśli wywołasz **`__unhook`** zdarzenia i program obsługi zdarzeń, który nie został już podłączony, nie będzie miał żadnego efektu.

W czasie kompilacji kompilator sprawdza, czy zdarzenie istnieje i sprawdza typ parametru z określoną obsługą.

Możesz wywoływać **`__hook`** i **`__unhook`** poza odbiornikiem zdarzeń, z wyjątkiem zdarzeń com.

Alternatywą dla użycia **`__unhook`** jest użycie operatora-=.

Aby uzyskać informacje na temat kodowania zdarzeń zarządzanych w nowej składni, zobacz [Event](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="example"></a>Przykład

Zobacz [Obsługa zdarzeń w natywnym kodzie C++](../cpp/event-handling-in-native-cpp.md) i [Obsługa zdarzeń w modelu COM](../cpp/event-handling-in-com.md) dla przykładów.

## <a name="see-also"></a>Zobacz także

[Służąc](../cpp/keywords-cpp.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__raise`](../cpp/raise.md)
