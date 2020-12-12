---
description: 'Dowiedz się więcej o: błąd kompilatora C3701'
title: Błąd kompilatora C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 8ebc8ac41091770a59876fb829d86997d7f5709c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228693"
---
# <a name="compiler-error-c3701"></a>Błąd kompilatora C3701

"Function": event_source nie ma żadnych zdarzeń

Podjęto próbę użycia [event_source](../../windows/attributes/event-source.md) na klasie, która nie ma metod zdarzeń. Aby naprawić ten błąd, Dodaj co najmniej jedno zdarzenie do klasy.

Poniższy przykład generuje C3701:

```cpp
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```
