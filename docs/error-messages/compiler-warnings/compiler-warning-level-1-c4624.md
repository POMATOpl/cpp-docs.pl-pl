---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4624'
title: Ostrzeżenie kompilatora (poziom 1) C4624
ms.date: 11/04/2016
f1_keywords:
- C4624
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
ms.openlocfilehash: d5869742b548c4a54efe08e686571123fc570517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281460"
---
# <a name="compiler-warning-level-1-c4624"></a>Ostrzeżenie kompilatora (poziom 1) C4624

"Klasa pochodna": destruktor został niejawnie zdefiniowany jako usunięty, ponieważ destruktor klasy bazowej jest niedostępny lub usunięty

Destruktor nie był dostępny ani usunięty w klasie bazowej i dlatego nie został wygenerowany dla klasy pochodnej. Każda próba utworzenia obiektu tego typu na stosie spowoduje błąd kompilatora.

Poniższy przykład generuje C4624 i pokazuje, jak to naprawić:

```cpp
// C4624.cpp
// compile with: /W1 /c
class B {
// Uncomment the following line to fix.
// public:
   ~B();
};

class D : public B {};   // C4624 B's destructor not public
```
