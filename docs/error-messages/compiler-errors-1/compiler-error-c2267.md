---
description: 'Dowiedz się więcej o: błąd kompilatora C2267'
title: Błąd kompilatora C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: df69073cbb1956033cf7d028c56e13018e4bbcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328411"
---
# <a name="compiler-error-c2267"></a>Błąd kompilatora C2267

"Function": funkcje statyczne z zakresem bloku są niedozwolone

Zadeklaruje funkcję lokalną **`static`** . Funkcje statyczne muszą mieć zakres globalny.

Poniższy przykład generuje C2267:

```cpp
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```
