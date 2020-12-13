---
description: 'Dowiedz się więcej o: błąd kompilatora C2054'
title: Błąd kompilatora C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: b86c805a5687679cfa4bb5ed667c3bcf3adbad94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341363"
---
# <a name="compiler-error-c2054"></a>Błąd kompilatora C2054

Oczekiwano znaku "(" po "Identyfikator"

Identyfikator funkcji jest używany w kontekście, który wymaga końcowych nawiasów.

Przyczyną tego błędu może być pominięcie znaku równości (=) w przypadku inicjalizacji złożonej.

Poniższy przykład generuje C2054:

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

Możliwe rozwiązanie:

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
