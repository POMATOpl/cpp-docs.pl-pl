---
description: 'Dowiedz się więcej o: błąd kompilatora C3465'
title: Błąd kompilatora C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: ab5d55b5e21241eb2bbab00524f3c81baaace88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113457"
---
# <a name="compiler-error-c3465"></a>Błąd kompilatora C3465

Aby użyć typu "Type", należy odwołać się do zestawu "Assembly"

Przekazywanie typu będzie działało dla aplikacji klienckiej do momentu ponownego skompilowania klienta. Po ponownym skompilowaniu wymagane jest odwołanie do każdego zestawu zawierającego definicję typu używanego w aplikacji klienckiej.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład kompiluje zestaw, który zawiera nową lokalizację typu.

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

Poniższy przykład kompiluje zestaw, który zawiera definicję typu, ale teraz zawiera składnię przekazywania dla tego typu.

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

Poniższy przykład generuje C3465.

```cpp
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```
