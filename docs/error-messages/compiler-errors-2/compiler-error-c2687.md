---
description: 'Dowiedz się więcej o: błąd kompilatora C2687'
title: Błąd kompilatora C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: 38996f2f31998ef96dd848915686adb1bf46c987
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220763"
---
# <a name="compiler-error-c2687"></a>Błąd kompilatora C2687

"Type": Deklaracja wyjątku nie może być typu "void" lub wskazuje niekompletny typ lub wskaźnik lub odwołanie do niekompletnego typu

Dla typu, który będzie częścią deklaracji wyjątku, musi być zdefiniowana, a nie void.

Poniższy przykład generuje C2687:

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Możliwe rozwiązanie:

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
