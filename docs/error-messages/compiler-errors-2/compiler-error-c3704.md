---
description: 'Dowiedz się więcej o: błąd kompilatora C3704'
title: Błąd kompilatora C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: aae489b2d8657a1e62adc654d148be6cd0403af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278184"
---
# <a name="compiler-error-c3704"></a>Błąd kompilatora C3704

"Function": Metoda vararg nie może wyzwalać zdarzeń

Podjęto próbę użycia [__event](../../cpp/event.md) na metodzie vararg. Aby naprawić ten błąd, Zastąp wywołanie wywołaniem, `fireEvent(int i, ...)` `fireEvent(int i)` jak pokazano w poniższym przykładzie kodu.

Poniższy przykład generuje C3704:

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
