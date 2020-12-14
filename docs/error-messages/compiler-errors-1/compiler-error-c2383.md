---
description: 'Dowiedz się więcej o: błąd kompilatora C2383'
title: Błąd kompilatora C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 862346d7f2bfe92a5d2182a7fe53f260b357ad0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185937"
---
# <a name="compiler-error-c2383"></a>Błąd kompilatora C2383

"*symbol*": argumenty domyślne nie są dozwolone w tym symbolu

Kompilator języka C++ nie zezwala na używanie argumentów domyślnych dla wskaźników do funkcji.

Ten kod został zaakceptowany przez kompilator Microsoft C++ w wersjach przed programem Visual Studio 2005, ale teraz zawiera błąd. W przypadku kodu działającego we wszystkich wersjach Visual C++ nie należy przypisywać wartości domyślnej do argumentu wskaźnika do funkcji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2383 i zawiera możliwe rozwiązanie:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
