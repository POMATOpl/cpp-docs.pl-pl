---
description: 'Dowiedz się więcej o: błąd kompilatora C3612'
title: Błąd kompilatora C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 332d4bae940a0c98b148fd6ba951a4f51d1bee27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223103"
---
# <a name="compiler-error-c3612"></a>Błąd kompilatora C3612

"Type": Klasa zapieczętowana nie może być abstrakcyjna

Typy zdefiniowane przy użyciu `value` są zapieczętowane domyślnie, a Klasa jest abstrakcyjna, chyba że implementuje wszystkie metody jej bazy. Zapieczętowana Klasa abstrakcyjna nie może być klasą bazową ani nie można jej utworzyć.

Aby uzyskać więcej informacji, zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3612:

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
