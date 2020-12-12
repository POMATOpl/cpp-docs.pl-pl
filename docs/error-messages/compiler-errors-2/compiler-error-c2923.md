---
description: 'Dowiedz się więcej o: błąd kompilatora C2923'
title: Błąd kompilatora C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 7897ba68998f88f82144278e79c97d8fec9f85d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270280"
---
# <a name="compiler-error-c2923"></a>Błąd kompilatora C2923

"Type": "identifier" nie jest prawidłowym argumentem typu szablonu dla parametru "param"

Lista argumentów nie zawiera typu wymaganego do utworzenia wystąpienia szablonu lub ogólnego. Sprawdź szablon lub deklarację ogólną.

Poniższy przykład generuje C2923:

```cpp
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

C2923 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```
