---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4142'
title: Ostrzeżenie kompilatora (poziom 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: d82403d79310d577cd45fe835cd486719ea0fdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115732"
---
# <a name="compiler-warning-level-1-c4142"></a>Ostrzeżenie kompilatora (poziom 1) C4142

niegroźna ponowna definicja typu

Typ jest ponownie definiowany w sposób, który nie ma wpływu na wygenerowany kod.

Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny:

- Funkcja członkowska klasy pochodnej ma inny typ zwracany od odpowiedniej funkcji członkowskiej klasy podstawowej.

- Typ zdefiniowany za pomocą **`typedef`** polecenia jest ponownie definiowany przy użyciu innej składni.

Poniższy przykład generuje C4142:

```c
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
