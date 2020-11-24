---
title: event_receiver (atrybut C++ COM)
description: Dowiedz się, jak używać atrybutu com rozszerzenia Microsoft C++ `event_receiver` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.openlocfilehash: 8ed6ef6113d72a9565b275dff4e035dc56f11e82
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483285"
---
# <a name="event_receiver-attribute"></a>Atrybut `event_receiver`

Tworzy odbiorcę zdarzeń (ujścia).

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Parametry

*`type`*\
Wyliczenie jednej z następujących wartości:

- `native` dla niezarządzanego kodu C/C++ (domyślnie dla klas natywnych).

- `com` dla kodu COM. Ta wartość wymaga uwzględnienia następujących plików nagłówkowych:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`layout_dependent`*\
Określ *`layout_dependent`* tylko wtedy, gdy `type` = **com**. *`layout_dependent`* jest wartością logiczną:

- **`true`** oznacza, że podpis delegatów w odbiorcy zdarzeń musi dokładnie pasować do tych, do których są one podłączane w źródle zdarzeń. Nazwy programu obsługi odbiornika zdarzeń muszą być zgodne z nazwami określonymi w odpowiednim interfejsie źródła zdarzenia. Użyj `coclass` kiedy *`layout_dependent`* is **`true`** . Jest nieco bardziej wydajny **`true`** .

- **`false`** (ustawienie domyślne) oznacza, że Konwencja wywoływania i Klasa magazynu ( `virtual` , `static` , i inne) nie muszą być zgodne z metodą zdarzenia i obsługą. Nazwy programów obsługi nie muszą również odpowiadać nazwom metod interfejsu źródła zdarzeń.

## <a name="remarks"></a>Uwagi

**`event_receiver`** Atrybut C++ określa, że Klasa lub struktura, do której ma zastosowanie, będzie odbiorcą zdarzeń przy użyciu ujednoliconego modelu zdarzeń języka Microsoft C++.

**`event_receiver`** jest używany z [`event_source`](event-source.md) atrybutami i [`__hook`](../../cpp/hook.md) [`__unhook`](../../cpp/unhook.md) słowami kluczowymi i. Służy `event_source` do tworzenia źródeł zdarzeń. Użyj **`__hook`** w metodach odbiorcy zdarzeń, aby skojarzyć metody odbiornika zdarzeń ("Hook") z zdarzeniami źródła zdarzeń. Użyj **`__unhook`** , aby usunąć skojarzenie.

*`layout_dependent`* jest określona tylko dla odbiorników zdarzeń COM ( `type` = **`com`** ). Wartość domyślna *`layout_dependent`* to **`false`** .

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|--|--|
| **Dotyczy** | **`class`**, **`struct`** |
| **Powtarzalność** | Nie |
| **Wymagane atrybuty** | `coclass` czasie *`layout_dependent`*=**`true`** |
| **Nieprawidłowe atrybuty** | Brak |

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz także

[Atrybuty kompilatora](compiler-attributes.md)\
[`event_source`](event-source.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Atrybuty klasy](class-attributes.md)
