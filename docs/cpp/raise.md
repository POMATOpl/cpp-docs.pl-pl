---
title: __raise
description: Dowiedz się, jak używać słowa kluczowego rozszerzenia języka Microsoft C++ `__raise` do obsługi zdarzeń natywnych.
ms.date: 11/20/2020
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.openlocfilehash: c9df602803062bc51b8c0cee13f17263cdc91786
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483153"
---
# <a name="__raise-keyword"></a>`__raise` kodu

Wyróżnia lokację wywołania zdarzenia.

> [!NOTE]
> Atrybuty zdarzeń w natywnym języku C++ są niezgodne ze standardem C++. Nie kompilują się po określeniu [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybu zgodności.

## <a name="syntax"></a>Składnia

> **`__raise`** *`method-declarator`* **`;`**

## <a name="remarks"></a>Uwagi

W kodzie zarządzanym zdarzenie może zostać wywołane tylko z klasy, w której jest zdefiniowane. Aby uzyskać więcej informacji, zobacz [`event`](../extensions/event-cpp-component-extensions.md).

Słowo kluczowe **`__raise`** powoduje, że błąd jest emitowany w przypadku wywołania niezdarzenia.

> [!NOTE]
> Klasa lub struktura z szablonem nie może zawierać zdarzeń.

## <a name="example"></a>Przykład

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>Zobacz także

[Służąc](../cpp/keywords-cpp.md)\
[Obsługa zdarzeń](../cpp/event-handling.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[Rozszerzenia składników dla platformy .NET i platformy uniwersalnej systemu Windows](../extensions/component-extensions-for-runtime-platforms.md)
