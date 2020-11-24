---
title: Obsługa zdarzeń
description: Dowiedz się, jak rozszerzenia Microsoft C++ obsługują zarówno obsługę zdarzeń COM, jak i natywną.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: de8cd6dfac2b83e850ec62ff88e192d1c60e427e
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483133"
---
# <a name="event-handling"></a>Obsługa zdarzeń

Obsługa zdarzeń jest przede wszystkim obsługiwana dla klas COM (klasy C++ implementujące obiekty COM, zazwyczaj przy użyciu klas ATL lub atrybutu [coclass](../windows/attributes/coclass.md) ). Aby uzyskać więcej informacji, zobacz [Obsługa zdarzeń w modelu COM](../cpp/event-handling-in-com.md).

Obsługa zdarzeń jest również obsługiwana dla natywnych klas języka C++ (klasy C++, które nie implementują obiektów COM). Obsługa natywnych zdarzeń C++ jest przestarzała i zostanie usunięta w przyszłej wersji. Aby uzyskać więcej informacji, zobacz [Obsługa zdarzeń w natywnym języku C++](../cpp/event-handling-in-native-cpp.md).

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

Obsługa zdarzeń obsługuje zarówno użycie pojedyncze, jak i wielowątkowości. Chroni dane przed jednoczesnym dostępem wielowątkowej. Klasy podklas można utworzyć z klas źródłowych zdarzeń lub odbiorników. Te podklasy obsługują rozszerzone źródła zdarzeń i otrzymywanie.

Kompilator języka Microsoft C++ zawiera atrybuty i słowa kluczowe do deklarowania zdarzeń i programów obsługi zdarzeń. Atrybuty i słowa kluczowe zdarzenia mogą być używane w programach CLR i w natywnych programach języka C++.

| Artykuł | Opis |
|--|--|
| [`event_source`](../windows/attributes/event-source.md) | Tworzy Źródło zdarzenia. |
| [`event_receiver`](../windows/attributes/event-receiver.md) | Tworzy odbiorcę zdarzeń (ujścia). |
| [`__event`](../cpp/event.md) | Deklaruje zdarzenie. |
| [`__raise`](../cpp/raise.md) | Wyróżnia lokację wywołania zdarzenia. |
| [`__hook`](../cpp/hook.md) | Kojarzy metodę procedury obsługi ze zdarzeniem. |
| [`__unhook`](../cpp/unhook.md) | Usuwa metodę procedury obsługi ze zdarzenia. |

## <a name="see-also"></a>Zobacz także

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
