---
description: 'Dowiedz się więcej o: błąd kompilatora C3533'
title: Błąd kompilatora C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 03506c5880cce18a27f16f0e05d3b231d14c9ce6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113198"
---
# <a name="compiler-error-c3533"></a>Błąd kompilatora C3533

"Type": parametr nie może mieć typu zawierającego element "Auto"

Nie można zadeklarować metody lub parametru szablonu za pomocą **`auto`** słowa kluczowego, jeśli jest włączona domyślna opcja [/Zc:](../../build/reference/zc-auto-deduce-variable-type.md) autokompilator.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Usuń **`auto`** słowo kluczowe z deklaracji parametru.

## <a name="examples"></a>Przykłady

Poniższy przykład daje C3533, ponieważ deklaruje parametr funkcji ze **`auto`** słowem kluczowym i jest kompilowany za pomocą **/Zc:** Auto.

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

Poniższy przykład daje C3533 w trybie C++ 14, ponieważ deklaruje parametr szablonu ze **`auto`** słowem kluczowym i jest kompilowany za pomocą **/Zc:** Auto. (W języku C++ 17 jest to poprawna definicja szablonu klasy z pojedynczym parametrem szablonu bez typu, którego typ jest wywnioskowany).

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto(wywnioskowanie typu zmiennej)](../../build/reference/zc-auto-deduce-variable-type.md)
