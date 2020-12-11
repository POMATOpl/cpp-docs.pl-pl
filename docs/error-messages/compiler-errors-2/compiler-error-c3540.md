---
description: 'Dowiedz się więcej o: błąd kompilatora C3540'
title: Błąd kompilatora C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 85106061b2631d3a392b05a50c49f24566cdd4cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112456"
---
# <a name="compiler-error-c3540"></a>Błąd kompilatora C3540

"Type": nie można zastosować operatora sizeof do typu, który zawiera element "Auto"

Nie można zastosować operatora [sizeof](../../cpp/sizeof-operator.md) do wskazanego typu, ponieważ zawiera on **`auto`** specyfikator.

## <a name="example"></a>Przykład

Poniższy przykład daje C3540.

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto(wywnioskowanie typu zmiennej)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof — Operator](../../cpp/sizeof-operator.md)
