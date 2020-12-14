---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4716'
title: Ostrzeżenie kompilatora (poziom 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 3ea67c6220cfda97989e4ea095856082608aab0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249077"
---
# <a name="compiler-warning-level-1-c4716"></a>Ostrzeżenie kompilatora (poziom 1) C4716

Funkcja "Function" musi zwracać wartość

Dana funkcja nie zwróciła wartości.

Tylko funkcje z typem zwracanym void mogą używać polecenia Return bez towarzyszącej wartości zwracanej.

Niezdefiniowana wartość zostanie zwrócona, gdy ta funkcja zostanie wywołana.

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md).

Poniższy przykład generuje C4716:

```cpp
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```
