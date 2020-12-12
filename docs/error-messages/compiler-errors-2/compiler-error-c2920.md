---
description: 'Dowiedz się więcej o: błąd kompilatora C2920'
title: Błąd kompilatora C2920
ms.date: 11/04/2016
f1_keywords:
- C2920
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
ms.openlocfilehash: 08c11832fc2241fb8fbebf7bda56db29bf181022
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270332"
---
# <a name="compiler-error-c2920"></a>Błąd kompilatora C2920

Ponowna definicja: "Class": szablon klasy lub generyczny został już zadeklarowany jako "Type"

Klasa generyczna lub szablonu ma wiele deklaracji, które nie są równoważne. Aby naprawić ten błąd, Użyj różnych nazw dla różnych typów lub Usuń ponowną definicję nazwy typu.

Poniższy przykład generuje C2920 i pokazuje, jak to naprawić:

```cpp
// C2920.cpp
// compile with: /c
typedef int TC1;
template <class T>
struct TC1 {};   // C2920
struct TC2 {};   // OK - fix by using a different name
```

C2920 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2920b.cpp
// compile with: /clr /c
typedef int GC1;
generic <class T>
ref struct GC1 {};   // C2920
ref struct GC2 {};   // OK - fix by using a different name
```
