---
description: 'Dowiedz się więcej o: błąd kompilatora C2942'
title: Błąd kompilatora C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: d68db30f1b70aed20e2501c88bddaf00bb330149
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249597"
---
# <a name="compiler-error-c2942"></a>Błąd kompilatora C2942

"Class": Identyfikator klasy typu jest ponownie zdefiniowany jako formalny argument funkcji

Nie można użyć klasy generycznej ani szablonu jako argumentu formalnego. Nie można przekazać argumentu bezpośrednio do konstruktora klasy generycznej lub szablonu.

Poniższy przykład generuje C2942:

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

C2942 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```
