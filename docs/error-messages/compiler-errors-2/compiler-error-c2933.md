---
title: Błąd kompilatora C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: 51889ababd646edebbaf1d0d1a1c608e7b068009
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233421"
---
# <a name="compiler-error-c2933"></a>Błąd kompilatora C2933

"Class": Identyfikator klasy typu został ponownie zdefiniowany jako składową typedef "identifier"

Nie można użyć klasy generycznej ani szablonu jako **`typedef`** elementu członkowskiego.

Poniższy przykład generuje C2933:

```cpp
// C2933.cpp
// compile with: /c
template<class T> struct TC { };
struct MyStruct {
   typedef int TC<int>;   // C2933
};

struct TC2 { };
struct MyStruct2 {
   typedef int TC2;
};
```

C2933 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2933b.cpp
// compile with: /clr /c
generic<class T> ref struct GC { };
struct MyStruct {
   typedef int GC<int>;   // C2933
};

ref struct GC2 { };
struct MyStruct2 {
   typedef int GC2;
};
```
