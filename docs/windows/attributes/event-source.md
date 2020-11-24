---
title: event_source (atrybut C++ COM)
description: Dowiedz się, jak używać atrybutu com rozszerzenia Microsoft C++ `event_source` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.openlocfilehash: 3cdfaaa86f8fc36bf0dc90d7961077546362a662
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483272"
---
# <a name="event_source-attribute"></a>Atrybut `event_source`

Tworzy Źródło zdarzenia.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parametry

*`type`*\
Wyliczenie jednej z następujących wartości:

- `native` dla niezarządzanego kodu C/C++ (domyślnie dla klas niezarządzanych).

- `com` dla kodu COM. Użyj, `coclass` gdy *`type`* = `com` . Ta wartość wymaga uwzględnienia następujących plików nagłówkowych:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`optimize`*\
Gdy *Typ* to `native` , możesz określić `optimize=size` , aby wskazać, że dla wszystkich zdarzeń w klasie lub (wartość domyślna) istnieje 4-bajtowe miejsce w magazynie (minimum) `optimize=speed` .

*`decorate`*\
Gdy *Typ* to `native` , można określić `decorate=false` , aby wskazać, że rozwinięta nazwa w scalonym *`.mrg`* pliku () nie powinna zawierać otaczającej nazwy klasy. [`/Fx`](../../build/reference/fx-merge-injected-code.md) umożliwia generowanie *`.mrg`* plików. `decorate=false`, który jest wartością domyślną, powoduje w pełni kwalifikowane nazwy typów w scalonym pliku.

## <a name="remarks"></a>Uwagi

**`event_source`** Atrybut C++ określa, że Klasa lub struktura, do której ma zastosowanie, będzie źródłem zdarzenia.

**`event_source`** jest używany w połączeniu z [`event_receiver`](event-receiver.md) atrybutem i [`__event`](../../cpp/event.md) słowem kluczowym. Służy `event_receiver` do tworzenia odbiorców zdarzeń. Użyj **`__event`** metod w ramach źródła zdarzeń, aby określić te metody jako zdarzenia.

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|--|--|
| **Dotyczy** | **`class`**, **`struct`** |
| **Powtarzalność** | Nie |
| **Wymagane atrybuty** | **`coclass`** czasie `type`=`com` |
| **Nieprawidłowe atrybuty** | Brak |

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz także

[Atrybuty kompilatora](compiler-attributes.md)\
[`event_receiver`](event-receiver.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Atrybuty klasy](class-attributes.md)
