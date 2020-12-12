---
description: 'Dowiedz się więcej o: błąd kompilatora C3765'
title: Błąd kompilatora C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 29de872030143ab33e1349f07ac3b81cb841e113
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234621"
---
# <a name="compiler-error-c3765"></a>Błąd kompilatora C3765

"Event": nie można zdefiniować zdarzenia w typie klasy/struktury "oznaczonej jako event_receiver

Jeśli klasa jest oznaczona przy użyciu atrybutu [event_receiver](../../windows/attributes/event-receiver.md) , Klasa nie może zawierać deklaracji [__event](../../cpp/event.md) .

Poniższy przykład generuje C3765:

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
