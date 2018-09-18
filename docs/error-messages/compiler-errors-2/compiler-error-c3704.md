---
title: Błąd kompilatora C3704 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4504534e3a53f37089f0b0ba045b7afde5a8065d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054990"
---
# <a name="compiler-error-c3704"></a>Błąd kompilatora C3704

'Funkcja': metoda vararg nie może wyzwalać zdarzeń

Podjęto próbę użycia [__event](../../cpp/event.md) na metoda vararg. Aby naprawić ten błąd, należy zastąpić `fireEvent(int i, ...)` wywołanie `fireEvent(int i)` wywołania, jak pokazano w następującym przykładzie kodu.

Poniższy przykład spowoduje wygenerowanie C3704:

```
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