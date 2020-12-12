---
description: 'Dowiedz się więcej o: błąd kompilatora C2429'
title: Błąd kompilatora C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 3c16a2a430e8050103c3903cf1355de089252ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190136"
---
# <a name="compiler-error-c2429"></a>Błąd kompilatora C2429

> "*funkcja języka*" wymaga flagi kompilatora "*Option kompilatora*"

Funkcja Language wymaga określonej opcji kompilatora, aby uzyskać pomoc techniczną.

Błąd **C2429: funkcja języka "nested-Namespace-Definition" wymaga flagi kompilatora "/std: c++ 17"** jest generowana w przypadku próby zdefiniowania *złożonej przestrzeni nazw*, która zawiera jedną lub więcej nazw zagnieżdżonych zakresów nazw, począwszy od programu Visual Studio 2015 Update 5. (W programie Visual Studio 2017 w wersji 15,3 wymagany jest przełącznik **/std: c + +** ). Definicje złożonych przestrzeni nazw są niedozwolone w języku C++ przed C++ 17. Kompilator obsługuje definicje przestrzeni nazw złożonych, gdy jest określona opcja kompilatora [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) :

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
