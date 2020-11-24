---
title: __event
description: Dowiedz się, jak używać słowa kluczowego rozszerzenia języka Microsoft C++ `__event` do obsługi zdarzeń natywnych.
ms.date: 11/20/2020
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.openlocfilehash: 1678699d9b66c1a49dd5ca2bb019a6229c37a031
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483147"
---
# <a name="__event-keyword"></a>`__event` kodu

Deklaruje zdarzenie.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

> **`__event`** *`member-function-declarator`* **`;`**\
> **`__event`** **`__interface`** *`interface-specifier`* **`;`**\
> **`__event`** *`data-member-declarator`* **`;`**

## <a name="remarks"></a>Uwagi

Słowo kluczowe specyficzne dla firmy Microsoft **`__event`** można zastosować do deklaracji funkcji składowej, deklaracji interfejsu lub deklaracji elementu członkowskiego danych. Nie można jednak użyć **`__event`** słowa kluczowego, aby zakwalifikować element członkowski klasy zagnieżdżonej.

W zależności od tego, czy źródło i odbiorca zdarzenia są natywne C++, COM czy zarządzane (.NET Framework), można użyć następujących konstrukcji jako zdarzeń:

| Natywny język C++ | Model COM | Zarządzane (.NET Framework) |
|--|--|--|
| funkcja członkowska | - | method |
| - | interface | - |
| - | - | element członkowski danych |

Użyj [`__hook`](../cpp/hook.md) w odbiorniku zdarzeń, aby skojarzyć funkcję składową programu obsługi z funkcją członkowską zdarzenia. Po utworzeniu zdarzenia za pomocą **`__event`** słowa kluczowego, wszystkie procedury obsługi zdarzeń podłączane do tego zdarzenia zostaną wywołane po wywołaniu zdarzenia.

**`__event`** Deklaracja funkcji składowej nie może mieć definicji; definicja jest generowana niejawnie, więc funkcja członkowska zdarzenia może być wywoływana, tak jakby była to jakakolwiek zwykła funkcja członkowska.

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="native-events"></a>Zdarzenia natywne

Zdarzenia natywne są funkcjami składowymi. Typ zwracany jest zwykle `HRESULT` lub **`void`** , ale może być dowolnym typem całkowitym, łącznie z **`enum`** . Gdy zdarzenie używa całkowitego typu zwracanego, warunek błędu jest definiowany, gdy program obsługi zdarzeń zwraca wartość różną od zera. W takim przypadku zgłoszone zdarzenie wywołuje innych delegatów.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Zobacz [Obsługa zdarzeń w natywnym języku C++](../cpp/event-handling-in-native-cpp.md) dla przykładowego kodu.

## <a name="com-events"></a>Zdarzenia COM

Zdarzenia COM są interfejsami. Parametry funkcji elementu członkowskiego w interfejsie źródłowym zdarzenia powinny znajdować się *w* parametrach, ale nie są rygorystyczne wymuszane. Wynika to z faktu, że parametr *out* nie jest przydatny podczas multiemisji. Ostrzeżenie poziomu 1 jest wydawane w przypadku użycia parametru *out* .

Typ zwracany jest zwykle `HRESULT` lub **`void`** , ale może być dowolnym typem całkowitym, w tym **`enum`** . Gdy zdarzenie używa całkowitego typu zwracanego, a procedura obsługi zdarzeń zwraca wartość różną od zera, jest to warunek błędu. Zgłoszone zdarzenie przerywa wywołania do innych delegatów. Kompilator automatycznie oznacza interfejs źródła zdarzeń jako element [`source`](../windows/attributes/source-cpp.md) w wygenerowanym IDL.

[`__interface`](../cpp/interface.md)Słowo kluczowe jest zawsze wymagane po **`__event`** dla źródła zdarzenia com.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Zobacz [Obsługa zdarzeń w modelu COM](../cpp/event-handling-in-com.md) dla przykładowego kodu.

## <a name="managed-events"></a>Zdarzenia zarządzane

Aby uzyskać informacje na temat kodowania zdarzeń w nowej składni, zobacz [Event](../extensions/event-cpp-component-extensions.md).

Zdarzenia zarządzane to składowe danych lub funkcje członkowskie. W przypadku użycia ze zdarzeniem zwracany typ delegata musi być zgodny z [Common Language Specification](/dotnet/standard/language-independence-and-language-independent-components). Zwracany typ procedury obsługi zdarzeń musi być zgodny z typem zwracanym delegata. Aby uzyskać więcej informacji na temat delegatów, zobacz [delegats and Events](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md). Jeśli zarządzanym zdarzeniem jest element członkowski danych, jego typ musi być wskaźnikiem do delegata.

W .NET Framework można traktować składową danych tak, jakby była to sama metoda (czyli `Invoke` Metoda odpowiedniego delegata). W tym celu należy wstępnie zdefiniować typ delegata do deklarowania elementu członkowskiego danych zdarzenia zarządzanego. W przeciwieństwie do zarządzanej metody zdarzenia niejawnie definiuje odpowiadającą zarządzaną delegata, jeśli nie jest jeszcze zdefiniowana. Na przykład można zadeklarować wartość zdarzenia, taką jak `OnClick` zdarzenie w następujący sposób:

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

Gdy niejawnie deklaruje zdarzenie zarządzane, można określić `add` i `remove` metody dostępu, które są wywoływane, gdy programy obsługi zdarzeń są dodawane lub usuwane. Można również zdefiniować funkcję członkowską, która wywołuje (podnosi) zdarzenie spoza klasy.

## <a name="example-native-events"></a>Przykład: Zdarzenia natywne

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>Przykład: zdarzenia COM

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>Zobacz także

[Służąc](../cpp/keywords-cpp.md)\
[Obsługa zdarzeń](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
