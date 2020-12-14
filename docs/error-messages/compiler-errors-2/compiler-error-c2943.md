---
description: 'Dowiedz się więcej o: błąd kompilatora C2943'
title: Błąd kompilatora C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: f85000ae554e25f2ca783b605b036abb3f04eadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249584"
---
# <a name="compiler-error-c2943"></a>Błąd kompilatora C2943

"Class": Identyfikator klasy typu, który został ponownie zdefiniowany jako argument typu szablonu

Nie można użyć klasy generycznej ani szablonu zamiast symbolu jako argumentu typu ogólnego lub szablonu.

Poniższy przykład generuje C2943:

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
