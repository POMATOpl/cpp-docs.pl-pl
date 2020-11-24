---
title: __hook
description: Dowiedz się, jak używać słowa kluczowego rozszerzenia języka Microsoft C++ `__hook` do obsługi zdarzeń natywnych.
ms.date: 11/20/2020
f1_keywords:
- __hook_cpp
- __hook
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.openlocfilehash: 2a2bde221c53f0e1d420e2ab3a88eb299f6c284c
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483259"
---
# <a name="__hook-keyword"></a>`__hook` kodu

Kojarzy metodę procedury obsługi ze zdarzeniem.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

```cpp
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);

long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>Parametry

*`&SourceClass::EventMethod`*\
Wskaźnik do metody zdarzenia, do której zostanie poddana metoda obsługi zdarzeń:

- Natywne zdarzenia języka C++: *`SourceClass`* to Klasa źródła zdarzeń, która *`EventMethod`* jest zdarzeniem.

- Zdarzenia COM: *`SourceClass`* jest interfejsem źródła zdarzeń i *`EventMethod`* jest jedną z jej metod.

- Zdarzenia zarządzane: *`SourceClass`* to Klasa źródła zdarzeń, która *`EventMethod`* jest zdarzeniem.

*`interface`*\
Nazwa interfejsu podłączanego do *`receiver`* , tylko dla odbiorników zdarzeń com, w których *`layout_dependent`* [`event_receiver`](../windows/attributes/event-receiver.md) jest parametr atrybutu **`true`** .

*`source`*\
Wskaźnik do wystąpienia źródła zdarzeń. W zależności od kodu `type` określonego w `event_receiver` , *`source`* może być jednym z następujących typów:

- Natywny wskaźnik obiektu źródła zdarzenia.

- `IUnknown`Wskaźnik oparty na (źródle com).

- Wskaźnik obiektu zarządzanego (dla zdarzeń zarządzanych).

*`&ReceiverClass::HandlerMethod`*\
Wskaźnik do metody obsługi zdarzeń, który ma zostać poddany zdarzeniu. Procedura obsługi jest określona jako metoda klasy lub odwołania do tego samego. Jeśli nie określisz nazwy klasy, przyjmuje się, że **`__hook`** Klasa jest tą, z której jest wywoływana.

- Natywne zdarzenia języka C++: *`ReceiverClass`* to Klasa odbiorcy zdarzeń i `HandlerMethod` jest programem obsługi.

- Zdarzenia COM: *`ReceiverClass`* to interfejs odbiorcy zdarzeń i *`HandlerMethod`* jest jednym z jego obsługi.

- Zdarzenia zarządzane: *`ReceiverClass`* to Klasa odbiorcy zdarzeń i *`HandlerMethod`* jest programem obsługi.

*`receiver`*\
Obowiązkowe Wskaźnik do wystąpienia klasy odbiorcy zdarzeń. Jeśli odbiornik nie zostanie określony, wartością domyślną jest Klasa odbiornika lub struktura, w której **`__hook`** jest wywoływana.

## <a name="usage"></a>Użycie

Można używać w dowolnym zakresie funkcji, w tym Main, poza klasą odbiorcy zdarzeń.

## <a name="remarks"></a>Uwagi

Użyj funkcji wewnętrznej **`__hook`** w odbiorniku zdarzenia, aby skojarzyć lub podpiąć metodę procedury obsługi przy użyciu metody zdarzenia. Określony program obsługi jest następnie wywoływany, gdy źródło zgłasza określone zdarzenie. Można podłączyć kilka programów obsługi do pojedynczego zdarzenia lub podłączyć kilka zdarzeń do jednego programu obsługi.

Istnieją dwie formy **`__hook`** . W większości przypadków można użyć pierwszego (czterech argumentów) formularza, w szczególności dla odbiorników zdarzeń COM, w których parametr *layout_dependent* [`event_receiver`](../windows/attributes/event-receiver.md) atrybutu ma wartość **`false`** .

W takich przypadkach nie trzeba dołączać wszystkich metod w interfejsie przed wyzwoleniem zdarzenia na jednej z metod. Musisz tylko podłączyć metodę obsługującą zdarzenie. Można użyć drugiego (dwóch argumentów) formularza **`__hook`** tylko dla odbiornika zdarzeń com, w którym *`layout_dependent`* **`= true`** .

**`__hook`** Zwraca wartość długą. Wartość zwrotna niezerowa wskazuje, że wystąpił błąd (zdarzenia zarządzane zgłasza wyjątek).

Kompilator sprawdza obecność zdarzenia i sygnatura zdarzenia zgadza się z podpisem delegata.

Możesz wywoływać **`__hook`** i **`__unhook`** poza odbiornikiem zdarzeń, z wyjątkiem zdarzeń com.

Alternatywą dla użycia **`__hook`** jest użycie operatora + =.

Aby uzyskać informacje na temat kodowania zdarzeń zarządzanych w nowej składni, zobacz [`event`](../extensions/event-cpp-component-extensions.md) .

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="example"></a>Przykład

Zobacz [Obsługa zdarzeń w natywnym kodzie C++](../cpp/event-handling-in-native-cpp.md) i [Obsługa zdarzeń w modelu COM](../cpp/event-handling-in-com.md) dla przykładów.

## <a name="see-also"></a>Zobacz także

[Służąc](../cpp/keywords-cpp.md)\
[Obsługa zdarzeń](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
